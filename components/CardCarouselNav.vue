<template>
    <div>
        <span class="carousel-index text-white mt-1">
            {{i}} of {{amount}}
        </span>

        <span class="card-carousel-nav left text-white">
            &lsaquo;
        </span>

        <span class="card-carousel-nav right text-white">
            &rsaquo;
        </span>
    </div>

</template>


<script>
export default {
    props: ['amount', 'i'],
}
</script>


<style scoped lang="scss">
@import '~/assets/css/main.scss';

.card-carousel-nav{
    top: 10px;
    right: 10px;
    padding: 0px 10px 0px 10px;
    font-weight: 600;
    font-size: 16px;
    border-radius: $border-radius-sm;
    position: absolute;
    background-color: #3F3A50;
    border: 1px solid rgba(255, 255, 255, .2);
    font-family: 'Overpass', sans-serif;
}

.left {
    margin-right: 2rem;
}

.carousel-index {
    top: 10px;
    right: 10px;
    padding: 1px 10px 1px 10px;
    font-weight: 400;
    font-size: 12px;
    border-radius: $border-radius-sm;
    position: absolute;
    font-family: 'Overpass', sans-serif;
    margin-right: 4rem;
}
</style>