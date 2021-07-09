<template>
    <footer>
        <div class="inner-footer py-5 px-4 row">
            <Logo color="white" class="col-md-2" />
            <div class="footer-container col-md-4">
                <h1 class="mb-2">Branch Details</h1>
                <div class="row">
                    <div class="col-sm-6">
                        <h2 class="mb-2">Address</h2>
                        <p>101 Business Street</p>
                        <p>Business Town</p>
                        <p>Business County</p>
                        <p>BU51 N55</p>
                    </div>
                    <div class="col-sm-6">
                        <h2 class="mb-2">Opening Times</h2>
                        <div class="row">
                            <span class="col-sm-5">Weekdays</span>
                            <span class="col-sm-7">09:00 - 18:00</span>
                        </div>

                        <div class="row">
                            <span class="col-sm-5">Saturday</span>
                            <span class="col-sm-7">10:00 - 17:00</span>
                        </div>

                        <div class="row">
                            <span class="col-sm-5">Sunday</span>
                            <span class="col-sm-7">10:00 - 16:00</span>
                        </div>
            
                    </div>
                    <div class="col-sm-6">
                        <h2 class="mb-2 mt-3">Telephone</h2>
                        <a>01234 56789</a>
                    </div>
                    <div class="col-sm-6 mt-3">
                        <h2 class="mb-2">Email</h2>
                        <a>enquiries@cardeal.co.uk</a>
                    </div>
                </div>
            </div>

            <div class="footer-container col-md-3">
                <h1>Popular Brands</h1>
                <div class="row mt-3">
                    <div class="col-md-6 text-muted mb-2">Audi</div>
                    <div class="col-md-6 text-muted mb-2">Mini</div>
                    <div class="col-md-6 text-muted mb-2">BMW</div>
                    <div class="col-md-6 text-muted mb-2">Peugeot</div>
                    <div class="col-md-6 text-muted mb-2">Fiat</div>
                    <div class="col-md-6 text-muted mb-2">SEAT</div>
                    <div class="col-md-6 text-muted mb-2">Land Rover</div>
                    <div class="col-md-6 text-muted mb-2">Vauxhall</div>
                    <div class="col-md-6 text-muted mb-2">Mercedes-Benz</div>
                    <div class="col-md-6 text-muted mb-2">Volkswagen</div>

                </div>
            </div>

            <div class="footer-container col-md-3">
                <h1>Site Map</h1>
                <ul class="footer-list mt-3">
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">Home</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link nav-link-activate" to="/">Our cars</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">Sell your car</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">Apply for finance </NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">About us</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">Blog</NuxtLink>
                    </li>
                    <li class="mb-2">
                        <NuxtLink class="footer-link text-muted" to="/">Contact</NuxtLink>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>


<style scoped>

 footer{
    box-sizing: border-box;
    background-color: #282338;
    border-radius: 0 75px 0 0;
 }
 .inner-footer {
    color: white;
 }

.footer-link .footer-list{
    line-height: 24px;
}


</style>