<template>
    <div class="flexbox-container justify-content-between align-center my-5 mx-3">
        <a class="bottom-content-text-link flexbox-item-md-2 flexbox-item-lg-3" href="#navbar">Back to top</a>
        <div class="my-auto flexbox-item-md-7 flexbox-item-lg-6">
            <button class="button-type"
                :class="{
                    'active': carType == 'back'
                }"
                @click="changeResult('back')">
                    &lsaquo;
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'one'
                }"
                @click="changeResult('one')">
                1
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'two'
                }"
                @click="changeResult('two')">
                2
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'three'
                }"
                @click="changeResult('three')">
                3
            </button>
            <button class="button-type border-strong"
                :class="{
                    'active': carType == 'next',

                }"
                @click="changeResult('next')">
               <strong> &rsaquo;</strong>
            </button>

            <button class="button-type"
                :class="{
                    'active': carType == 'end'
                }"
                @click="changeResult('end')">
                &rsaquo;&rsaquo;
            </button>
        </div>


        <select class="sort-cars flexbox-item-lg-2">
            <option value="lowestPrice">Lowest price</option>
            <option value="highestPrice">Highest price</option>
        </select>

    </div>
</template>

<script>
export default {
    props: ['carQuantity'],
    data() {
        return {
            carType: 'all',
        };
    },
    methods: {
        changeResult: function(value){
            this.carType = value;
            this.$emit('classificationData', value);
        }
    }
}
</script>

<style scoped lang="scss">
@import '~/assets/css/main.scss';

.flexbox-container {
    a {
        text-decoration: underline;
        color: $text-grey-color;
    }

    .button-type {
        padding: 2px 25px 2px 25px;
        border-radius: $border-radius-md;
        cursor: pointer;
        margin-right: 5px;
        color: $text-grey-color;
        border: solid 1px $border-grey-color;
        background-color: #FFFFFF;
        height: 30px;
        font-size: 16px;
    }

    .active {
        color: #FFFFFF;
        background-color: $primary-color;
        border: solid 1px $primary-color !important;
    }

    .border-strong{
        border: 1px solid black;
    }

    .sort-cars{
        float: right;
        border-radius: $border-radius-lg;
        background-color: $background-white-color;
        padding: 13px;
        border: none;
        margin-left: auto;
    }
}
</style>