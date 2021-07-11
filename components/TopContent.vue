<template>
    <div>
        <div class="flexbox-container align-center my-5 pr-4">
            <span class="car-quantaty-text my-auto mr-5 ml-2">
                <span class="d-none-tablet">
                    Showing
                </span>
                 {{carQuantity}} cars
            </span>
            <button class="button-type my-auto"
                :class="{
                    'active': carType == 'all'
                }"
                @click="changeResult('all')">
                All
            </button>
            <button class="button-type my-auto"
                :class="{
                    'active': carType == 'used'
                }"
                @click="changeResult('used')">
                Used
            </button>
            <button class="button-type my-auto"
                :class="{
                    'active': carType == 'new'
                }"
                @click="changeResult('new')">
                New
            </button>
            <button class="button-type my-auto"
                :class="{
                    'active': carType == 'offers'
                }"
                @click="changeResult('offers')">
                Offers
            </button>

        <select class="sort-cars">
                <option value="lowestPrice">Lowest price</option>
                <option value="highestPrice">Highest price</option>
            </select>
        </div>
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

.button-type {
    padding: 2px 25px 2px 25px;
    border-radius: $border-radius-md;
    cursor: pointer;
    margin-right: 5px;
    color: $text-grey-color;
    border: solid 1px $border-grey-color;
    background-color: #FFFFFF;
    height: 30px;
}

.active {
    color: #FFFFFF;
    background-color: $primary-color;
    border: solid 1px $primary-color;
}

.car-quantaty-text{
    font-weight: 700;
    font-size: 18px;
    font-family: 'Overpass', sans-serif;
}

.sort-cars{
    float: right;
    border-radius: $border-radius-lg;
    background-color: $background-white-color;
    padding: 13px;
    border: none;
    margin-left: auto;
}

</style>