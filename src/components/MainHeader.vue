<template>
    <div id="header">
        <header>
            <router-link to="/">
                <img src="../assets/images/surfhouse-logo.png" alt="surfhouse logo">
            </router-link>
            
            <div class="basket-container">
                <div class="login">
                    <button>LOG IN</button>
                    <button>WISH LIST(0)</button>
                </div>
                
                <div class="basket">
                    <img src="../assets/images/icon-cart.png" alt="basket">
                    <div class="detail">
                        <p class="price">€1,459.50</p>
                        <p class="items">2 items</p>
                    </div>

                    <button class="btn-view">VIEW CART</button>
                    <button class="btn-checkout">CHECKOUT</button>
                </div>

                <div class="search">
                    <form>
                        <input type="text" placeholder="SEARCH" name="search">
                        <button type="submit"><i class="fa fa-search"></i></button>
                    </form>
                </div>
            </div>
        </header>
    </div>
</template>
        

<script>
export default {
  name: 'MainHeader'
}
</script>