<template>
    <header>
        <nav id="navbar" class="justify-content-between flexbox-container mx-3 align-center">

            <div class="flexbox-item-lg-3">
                <Logo color="black" class="mr-3" />
                <div class="nav-icon text-disabled my-auto">
                    <StarOutlineIcon /> <span class="ml-1 mr-2">0</span>
                </div> 
                <div class="nav-icon">
                    <RestoreIcon /> <span class="ml-1 mr-2">10</span>
                </div>       
            
            </div>
            
            <ul class="flexbox-item-6 d-none-tablet">
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
            <div class="flexbox-item-lg-3">
                <button class="nav-button mx-2" to="/">
                    Call us
                </button>
            
                <button class="nav-button mx-2" to="/">
                    Email us
                </button>
            </div>
         <!-- <MenuIcon /> -->
        </nav>
    </header>
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

    nav {
        height: 100px;
        background-color: #FFFFFF;
        align-items: center;

        .nav-icon{
            display:contents
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
            color: black;
            float: right;
            font-family: 'Overpass', sans-serif;
        }
    }

</style>