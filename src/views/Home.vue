<template>
  <div id="home">
    <Hero/>
    <ProductSection/>
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero.vue'
import ProductSection from '@/components/ProductSection.vue'
export default {
  name: 'home',
  components: {
    Hero,
    ProductSection
  }
}
</script>
