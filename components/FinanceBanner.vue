<template>
    <div id="financeBanner" class="banner-container py-4">
        <div class="text-white banner mx-4">
            <h4 class="banner-title">Finance a new used car </h4>
            <p class="banner-text">
                Adjust the options to find the finance arrangement that suits you.
            </p>
        </div>
        
    </div>
</template>


<style scoped lang="scss">
@import '~/assets/css/main.scss';

.banner-container {
    background-color: $banner-dark-color;
    border-radius: 0 0 0 50px;
    position: relative;

    &::before{
        content: ' ';
        display: block;
        position: absolute;
        width: 380px;
        height: 100%;
        top: 0;
        left: 0;
        background-color: #FFFFFF;
        opacity: 20%;
        border-radius: 0 0  150px 50px;
    }

    .banner {
        .banner-title {
            font-size: 18px;
            font-weight: 700;
            font-family: 'Overpass', sans-serif;
        }
         .banner-text {
            line-height: 24px;
            width: 300px ;
            font-size: 16px;
            font-weight: 400;
            font-family: 'Overpass', sans-serif;
        }
    }

    

}

</style> 