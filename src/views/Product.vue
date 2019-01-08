<template>
  <div id="product" v-if="product">
    <div class="product">
      <div class="product__images">
        <img :src="product.productImg" alt="product">

        <div class="product__images__slider">
          <button><i class="fas fa-angle-left"></i></button>
          <img :src="product.productImg" alt="product">
          <img :src="product.productImg" alt="product">
          <img :src="product.productImg" alt="product">
          <button><i class="fas fa-angle-right"></i></button>
        </div>
      </div>

      <div class="product__info">
        <div class="product__header">
          <h1>{{product.productTitle}}</h1>
          <h3>{{product.productPrice}}</h3>
        </div>
        <hr>
        <div class="product__overview">
          <h4>QUICK OVERVIEW:</h4>
          <p>{{product.productText}}</p>
        </div>
        <hr>
        <div class="product__size">
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
        <div class="product__length">
          <h4>LENGTH</h4>
          <button>32</button>
          <button>34</button>
        </div>
        <hr>
        <div class="product__add">
          <div class="product__add__quantity">
            <h4>Quantity:</h4>
            <form>
              <input type="text" placeholder="1">
              <button>+</button>
            </form>
          </div>

          <button>ADD TO CART</button>

          <div class="product__add__share">
            <a href="#">+ Add to Wishlist</a> <br>
            <a href="#">+ Add to Compare</a> <br>
            <a href="#">+ Email to a Friend</a>
          </div>
        </div>
      </div>
    </div>

    <div class="tabbar">
      <div class="tabbar__tabs">
        <button v-on:click="tabitem=1" class="tabbar__tabs__single">PRODUCT DESCRIPTION</button>
        <button v-on:click="tabitem=2" class="tabbar__tabs__single">ADDITIONAL INFORMATION</button>
        <button v-on:click="tabitem=3" class="tabbar__tabs__single">REVIEWS</button>
        <button v-on:click="tabitem=4" class="tabbar__tabs__single">PRODUCTS TAGS</button>
      </div>

      <div class="tabbar__details">
        <div v-if="tabitem === 1">
          <p>Here is the PRODUCT DESCRIPTION. There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. <br>
          <br>- 6.1 oz. 100% preshrunk heavyweight cotton
          <br>- Shoulder-to-shoulder taping
          <br>- Double-needle sleeves and bottom hem</p>
        </div>

        <div v-if="tabitem === 2">
          <p>Now you are in the ADDITIONAL INFORMATION. There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. <br>
          Here is the PRODUCT DESCRIPTION. There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text.</p>
        </div>

        <div v-if="tabitem === 3">
          <p>The REVIEWS you see here. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable.</p>
        </div>

        <div v-if="tabitem === 4">
          <p>The PRODUCTS TAG is:<br><br>
          - Kitesurf <br>
          - Super <br>
          - Hot water <br>
          - Woman</p>
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
      product: null,
      tabitem: 1
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