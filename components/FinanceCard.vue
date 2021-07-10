<template>
    <div class="mt-3 flexbox-item-5 mr-2"> 
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

button {
    background-color: #FFFFFF;
    padding: 3px 57px 3px 57px;
    border-radius: 16px;
    border: none;
    height: 80px;
    box-sizing: border-box;


    .finance-title {
        display: block;
        font-size: 16px
    }

    .finance-text {
        display: block;
        font-size: 18px;
        font-family: 'Overpass', sans-serif;;
    }
}


</style>
