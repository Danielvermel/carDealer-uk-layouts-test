<template>
    <div class="banner-container">
        <div class="col-md-3 text-white banner">
            <span class="banner-title">Finance a new used car </span>
            <p class="banner-text text-block">
                Adjust the options to find the finance arrangement that suits you.
            </p>
        </div>
        
    </div>
</template>


<style scoped>

.banner-container {
    background-color: #282338;
    width: 100%;
    padding: 30px 10px;
    border-radius: 0 0 0 70px;
    position: relative;
        
   
}

.banner-container::before{
    content: ' ';
    display: block;
    position: absolute;
    width: 400px;
    height: 100%;
    top: 0;
    left: 0;
    background-color: #FFFFFF;
    opacity: 20%;
    border-radius: 0 0  150px 50px;
}

.bannert-title .bannert-text {
    z-index: 2;
    color: #FFFFFF;
}

</style> 