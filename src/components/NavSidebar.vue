<template>
    <div id="nav-sidebar">
        <button class="menu_button" v-on:click="openMenu">MENU</button>
        <nav id="navigation">
            <ul>
                <li><a href="#">ABOUT</a></li>
                <li><a href="#">APPAREL</a></li>
                <li><a href="#">SURF APPAREL</a></li>
                <li><a href="#">WINDSURF</a></li>
                <li><a href="#">KITESURF</a></li>
                <li><a href="#">ACCESSORIES</a></li>
                <li><a href="#">SALE</a></li>
                <li><a href="#">BRANDS</a></li>
                <li><a href="#">BLOGS</a></li>
                <li><a href="#">GADGETS</a></li>
                <li><router-link to="/Contact">CONTACT</router-link></li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'NavSidebar',
    }
</script>