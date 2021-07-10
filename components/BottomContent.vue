<template>
    <header>

    <div class="flexbox-container">
        <a class="bottom-content-text-link flexbox-item-text" href="#navbar">Back to top</a>
        <div class="flexbox-item-buttons">
            <button class="button-type"
                :class="{
                    'active': carType == 'all'
                }"
                @click="changeResult('all')">
                <
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'used'
                }"
                @click="changeResult('used')">
                1
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'new'
                }"
                @click="changeResult('new')">
                2
            </button>
            <button class="button-type"
                :class="{
                    'active': carType == 'offers'
                }"
                @click="changeResult('offers')">
                3
            </button>
        </div>


       <select class="sort-cars flexbox-item-select">
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
    justify-content: space-between;
    align-items: center;
    margin: 40px 30px 40px 0;
}

.flexbox-item-text{
    width: 20%;
}

.flexbox-item-buttons{
    width: 60%;
    text-align: center;
}
.flexbox-item-select{
    width: 20%;
}

.bottom-content-text-link{
    text-decoration: underline;
    color: #55595D;
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