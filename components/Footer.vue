<template>
    <footer>
        <div class="text-white flexbox-container py-5 mx-4">
            <Logo color="white" class="flexbox-item-2" />
            <div class="footer-container flexbox-item-5">
                <h4 class="mb-4">Branch Details</h4>
                <div class="flexbox-container">
                    <div class="flexbox-item-6">
                        <h5 class="mb-2 text-disabled">Address</h5>
                        <p>101 Business Street</p>
                        <p>Business Town</p>
                        <p>Business County</p>
                        <p>BU51 N55</p>
                    </div>
                    <div class="flexbox-item-6">
                        <h5 class="mb-2 text-disabled">Opening Times</h5>
                        <div class="flexbox-container">
                            <span class="flexbox-item-5">Weekdays</span>
                            <span class="flexbox-item-7">09:00 - 18:00</span>
                        </div>

                        <div class="flexbox-container">
                            <span class="flexbox-item-5">Saturday</span>
                            <span class="flexbox-item-7">10:00 - 17:00</span>
                        </div>

                        <div class="flexbox-container">
                            <span class="flexbox-item-5">Sunday</span>
                            <span class="flexbox-item-7">10:00 - 16:00</span>
                        </div>
            
                    </div>
                    <div class="flexbox-item-6 mt-3">
                        <h5 class="mb-2 mt-3 text-disabled">Telephone</h5>
                        <a class="link">01234 56789</a>
                    </div>
                    <div class="flexbox-item-6 mt-3">
                        <h5 class="mb-2 mt-3 text-disabled">Email</h5>
                        <a class="link">enquiries@cardeal.co.uk</a>
                    </div>
                </div>
            </div>

            <div class="footer-container flexbox-item-3">
                <h4>Popular Brands</h4>
                <div class="flexbox-container mt-3">
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Audi</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Mini</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">BMW</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Peugeot</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Fiat</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">SEAT</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Land Rover</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Vauxhall</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Mercedes-Benz</NuxtLink>
                    <NuxtLink to="/" class="flexbox-item-6 text-disabled mb-2">Volkswagen</NuxtLink>

                </div>
            </div>

            <div class="footer-container flexbox-item-2 mx-auto">
                <h4>Site Map</h4>
                <ul class="m-0 p-0 mt-3">
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Home</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Our cars</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Sell your car</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Apply for finance </NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">About us</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Blog</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="text-disabled" to="/">Contact</NuxtLink>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>


<style scoped lang="scss">
@import '~/assets/css/main.scss';

 footer{
    box-sizing: border-box;
    background-color: $banner-dark-color;
    border-radius: 0 75px 0 0;

    h4 {
        font-size: 18px;
        font-family: 'Overpass', sans-serif;
    }

    h5{
        text-transform: uppercase;
        font-size: 12px;
        letter-spacing: 1px;
    }

    a {
        color: $primary-color;
        
        &:hover {
            color: #FFFFFF;
        }
    }

    .link {
        text-decoration: underline;
    }
 }

</style>