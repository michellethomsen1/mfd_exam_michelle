<template>
    <div id="product-section">
        <div class="head-slider">
            <h1>New products</h1>

            <div class="btn-slider">
                <button><i class="fas fa-angle-left"></i></button>
                <button><i class="fas fa-angle-right"></i></button>
            </div>
        </div>

        <div class="products">
            <div class="product-single" v-for="product in products" :key="product.id">
                <picture>
                    <router-link :to="`/product/${product.id}`"><img :src="product.productImg"></router-link>
                </picture>

                <div class="product-info">
                    <router-link :to="`/product/${product.id}`"><h3>{{product.productTitle}}</h3></router-link>

                    <div class="price">
                        <router-link :to="`/product/${product.id}`"><p>{{product.productPrice}}</p></router-link>
                        <p class="price-before">{{product.productPriceBefore}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'ProductSection',
        data () {
            return {
            products: null
            }
        },
        mounted () {
            this.getData()
        },
        methods: {
            getData () {
            axios
                .get('/listProducts.json')
                .then(response => (this.products = response.data.products))
            }
        }
    }
</script>