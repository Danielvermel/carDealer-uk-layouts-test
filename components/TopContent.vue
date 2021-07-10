<template>
    <header>

    <div class="flexbox-container">
        <span class="car-quantaty-text">Showing {{carQuantity}} cars</span>
        <button class="button-type"
            :class="{
                'active': carType == 'all'
            }"
            @click="changeResult('all')">
            All
        </button>
        <button class="button-type"
            :class="{
                'active': carType == 'used'
            }"
            @click="changeResult('used')">
            Used
        </button>
        <button class="button-type"
            :class="{
                'active': carType == 'new'
            }"
            @click="changeResult('new')">
            New
        </button>
        <button class="button-type"
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

    </header>
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

<style scoped> 

.flexbox-container {
    display: flex;
    align-items: center;
    margin: 40px 30px 40px 0;
}

.button-type {
    padding: 2px 25px 2px 25px;
    border-radius: 12px;
    cursor: pointer;
    margin-right: 5px;
    color: #55595D;
    border: solid 1px #D1D6E0;
    background-color: #FFFFFF;
}

.active {
    color: #FFFFFF;
    background-color: #7572FF;
    border: solid 1px #7572FF;
}

.car-quantaty-text{
    font-weight: 700;
    font-size: 18px;
    margin-right: 30px;
    font-family: 'Overpass', sans-serif;
}

.sort-cars{
    float: right;
    border-radius: 16px;
    background-color: #F6F7FB;
    padding: 13px;
    border: none;
    margin-left: auto;

}

</style>