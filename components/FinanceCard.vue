<template>
    <div class=" flexbox-item-finance-cards"> 
        <button class="mx-1 mb-3">
            <span class="finance-title">{{title}}</span>
            <span class="finance-text">{{text}}</span>
        </button>
    </div>
</template>

<script>
export default {
    props: ['title', 'text'],

}
</script>

<style scoped lang="scss">
@import '~/assets/css/main.scss';

.flexbox-item-finance-cards{
    flex:0 0 20%;
    button {
        background-color: #FFFFFF;
        border-radius: $border-radius-lg;
        border: none;
        height: 80px;
        box-sizing: border-box;
        width: 100%;


        .finance-title {
            font-size: 14px;
            display: block;
            font-weight: 400;
        }

        .finance-text {
            font-size: 18px;
            font-family: 'Overpass', sans-serif;
            display: block;
        }
    }
}




</style>
