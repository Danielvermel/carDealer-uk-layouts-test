<template>
    <div class="mt-3 flexbox-item-finance-cards mr-2"> 
        <button>
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
    width: 190px;

    button {
        background-color: #FFFFFF;
        border-radius: $border-radius-lg;
        border: none;
        height: 80px;
        box-sizing: border-box;
        width: inherit;


        .finance-title {
            font-size: 16px;
            display: block
        }

        .finance-text {
            font-size: 18px;
            font-family: 'Overpass', sans-serif;
            display: block;
        }
    }
}




</style>
