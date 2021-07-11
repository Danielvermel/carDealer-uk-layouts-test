<template>
    <nav class="navbar" id="navbar">

        <Logo color="black" />
        <div class="nav-icon">
            <StarOutlineIcon /> <span class="nav-icon-number">0</span>
        </div> 
        <div class="nav-icon">
            <RestoreIcon /> <span class="nav-icon-number">10</span>
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
        <div>
            <NuxtLink class="nav-button" to="/">
                <span> Call us</span>
            </NuxtLink>
        
            <NuxtLink class="nav-button" to="/">
                <span> Email us</span>
            </NuxtLink>
        </div>


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

<style scoped lang="scss">
@import '~/assets/css/main.scss';

    .navbar {
        margin: 0;
        height: 100px;
        background-color: #FFFFFF;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .nav-icon{
        display: flex;
    }
    
    .nav-icon-number{
        margin-left: 6px;
    }

    .nav-list {
        display: contents  
    }

    .nav-list li {
        display: inline-block;
        position: relative;
        padding-right: 20px;
    }

    .nav-links {
        line-height: 24px;
        font-size: 16px;
        align-content: center;
        color: $text-grey-color;
    }

    a {
        color: black
    }

    .nav-link-activate:before{
        content: '';
        width: 5px;
        height: 24px;
        top: -38px;
        background-color: $primary-color;
        border-radius: 0 0 $border-radius-lg $border-radius-lg;
        display: block;
        position: absolute;
        left: 50%;
        margin-left: -10px;
    }

    .nav-button{
        background-color: $brand-secondary-color;
        border-radius: $border-radius-lg;
        padding: 11px 25px 12px 25px;
        font-weight: 600;
        font-size: 16px;
        margin: 0px 5px;
        color: black
    }
</style>