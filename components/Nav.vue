<template>
    <nav class="navbar justify-content-between flexbox-container mx-3" id="navbar">

        <Logo color="black" />
        <div class="nav-icon">
            <StarOutlineIcon /> <span class="ml-2">0</span>
        </div> 
        <div class="nav-icon">
            <RestoreIcon /> <span class="ml-2">10</span>
        </div>       
        
        
        <ul>
            <li>
                <NuxtLink class="nav-link" to="/">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink class="nav-link activate" to="/">Our cars</NuxtLink>
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
            <button class="nav-button" to="/">
                Call us
            </button>
        
            <button class="nav-button" to="/">
                Email us
            </button>
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
        height: 100px;
        background-color: #FFFFFF;
        align-items: center;

        .nav-icon{
            display: flex;
        }

        ul {
            display: contents;

            li {
                display: inline-block;
                position: relative;

                .nav-link {
                    line-height: 24px;
                    font-size: 16px;
                    align-content: center;
                    color: $text-grey-color;

                    &:hover:before{
                        content: '';
                        width: 5px;
                        height: 24px;
                        top: -38px;
                        background-color: $primary-color;
                        border-radius: 0 0 $border-radius-lg $border-radius-lg;
                        display: block;
                        position: absolute;
                        left: 50%;
                    }
                }
            }
        }

        .nav-button{
            background-color: $brand-secondary-color;
            border-radius: $border-radius-lg;
            border: none;
            padding: 11px 25px 12px 25px;
            font-weight: 600;
            font-size: 16px;
            margin: 0px 5px;
            color: black;
        }
    }

</style>