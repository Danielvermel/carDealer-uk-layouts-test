<template>
    <span 
    class="nav-logo"
    :class="{
        'text-white': color === 'white',
        'text-black': color === 'black'
    }">
        CarDealer
        <sup class="nav-logo-sup">UK</sup>
    </span>
</template>

<script>
    export default {
        props: ['color']
    }
</script>

<style scoped>
    .nav-logo{
        font-size: 25px;
        font-weight: bold;
    }

    .text-white{
        color: #FFFFFF;
    }

    .text-black{
        color: #000000;
    }

    .nav-logo sup{
        color: #7572FF;
        font-size: 15px;
        margin-top: 20px;
        padding: 6.24px;
    }

</style>