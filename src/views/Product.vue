<template>
  <div id="product" v-if="product">
    <div class="product-images">
      <img :src="product.productImg" alt="product">

      <div class="product-images-slider">
        <button><i class="fas fa-angle-left"></i></button>
        <img :src="product.productImg" alt="product">
        <img :src="product.productImg" alt="product">
        <img :src="product.productImg" alt="product">
        <button><i class="fas fa-angle-right"></i></button>
      </div>
    </div>

    <div class="product-info">
      <div class="product-header">
        <h1>{{product.productTitle}}</h1>
        <h3>{{product.productPrice}}</h3>
      </div>
      <hr>
      <div class="product-overview">
        <h4>QUICK OVERVIEW:</h4>
        <p>{{product.productText}}</p>
      </div>
      <hr>
      <div class="product-size">
        <h4>SIZE</h4>
        <button>25</button>
        <button>26</button>
        <button>27</button>
        <button>28</button>
        <button>29</button>
        <button>30</button>
        <button>31</button>
        <button>32</button>
        <button>33</button>
      </div>
      <hr>
      <div class="product-length">
        <h4>LENGTH</h4>
        <button>32</button>
        <button>34</button>
      </div>
      <hr>
      <div class="product-add">

        <div class="quantity">
          <h4>Quantity:</h4>
          <form>
            <input type="text" placeholder="1">
            <button>+</button>
          </form>
        </div>

        <button>ADD TO CART</button>

        <div class="share">
          <a href="#">+ Add to Wishlist</a> <br>
          <a href="#">+ Add to Compare</a> <br>
          <a href="#">+ Email to a Friend</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'
  export default {
  name: 'Product',
  props: {
    maintitle: String
  },
  data () {
    return {
      product: null
    }
  },
  mounted () {
    this.getProductById()
  },
  methods: {
    getProductById () {
      let productId = this.$route.params.id
      console.log(typeof productId)
      axios
        .get('/listProducts.json')
        .then(response => {
          this.product = response.data.products.find(p => p.id === productId)
          console.log(this.product)
        })
        .catch(error => console.log(error))
    }
  }
}
</script>