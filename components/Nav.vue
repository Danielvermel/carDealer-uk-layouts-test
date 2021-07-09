<template>
    <nav class="navbar">

        <span class="nav-logo">CarDealer<sup class="nav-logo-sup">UK</sup></span>
        <div>
            <StarOutlineIcon /> 0
        </div> 
        <div>
            <RestoreIcon /> 10
        </div>       
        
        
        <ul class="nav-list">
            <li>
                <NuxtLink class="nav-link" to="/">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link nav-link-activate" to="/">Our cars</NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link" to="/">Sell your car</NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link" to="/">Apply for finance </NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link" to="/">About us</NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link" to="/">Blog</NuxtLink>
            </li>
             <li>
                <NuxtLink class="nav-link" to="/">Contact</NuxtLink>
            </li>
        </ul>
        <NuxtLink class="nav-button" to="/">
            <button> Call us</button>
        </NuxtLink>
        
        <NuxtLink class="nav-button" to="/">
            <button> Email us</button>
        </NuxtLink>

         <!-- <MenuIcon /> -->

    </nav>
</template>

<script>
import MenuIcon from 'vue-material-design-icons/Menu.vue';
import StarOutlineIcon from 'vue-material-design-icons/StarOutline.vue';
import RestoreIcon from 'vue-material-design-icons/Restore.vue';

    export default {

        components: {
        MenuIcon,
        RestoreIcon,
        StarOutlineIcon
        }
    }
</script>

<style scoped>
    .navbar {
        margin: 0;
        padding: 0;
        height: 100px;
        background-color: #FFFFFF;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .nav-logo{
        color: #000000;
        font-size: 25px;
        font-weight: bold;
        padding: 0px 33px;
    }
    .nav-logo sup{
        color: #7572FF;
        font-size: 15px;
        margin-top: 20px;
        padding: 6.24px;
    }

    .nav-list {
        list-style-type: none;   
    }

    .nav-list li {
        display: inline-block;
        position: relative;
        padding: 0 20px;
    }

    .nav-links {
        line-height: 24px;
        font-size: 16px;
        align-content: center;
        color: #55595D;
        
    }

    .nav-link-activate:before{
        content: '';
        width: 5px;
        height: 24px;
        top: -38px;
        background-color: #7572FF;
        border-radius: 0 0 15px 15px;
        display: block;
        position: absolute;
        left: 50%;
        margin-left: -5px;
    }

    .nav-button{
        background-color: #82F7FF;
        border-radius: 15px;
        padding: 11px 25px 12px 25px;
        font-weight: 600;
        font-size: 16px;
    }
</style>