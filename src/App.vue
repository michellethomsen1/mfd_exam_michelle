<template>
  <div id="app">
    <MainHeader/>

    <div class="grid-container">
      <div class="sidebar">
        <NavSidebar/>
        <TagsWidget/>
      </div>

      <router-view/>
    </div>

    <Brands/>
    <MainFooter/>
  </div>
</template>

<style lang="scss">
  //Import the scss styling
  @import "./assets/scss/main";
</style>

<script>
  // @ is an alias to /src
  import MainHeader from '@/components/MainHeader.vue';
  import NavSidebar from '@/components/NavSidebar.vue';
  import TagsWidget from '@/components/TagsWidget.vue';
  import Brands from '@/components/Brands.vue';
  import MainFooter from '@/components/MainFooter.vue';
  
  export default {
    components: {
      MainHeader,
      NavSidebar,
      TagsWidget,
      Brands,
      MainFooter
    }
  }
</script>

<style lang="scss">
  #nav {
    padding: 30px;
    a {
      font-weight: bold;
      color: #2c3e50;
      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
</style>
