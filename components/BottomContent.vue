<template>
    <header>

    <div class="flexbox-container">
        <a class="bottom-content-text-link flexbox-item-text" href="#navbar">Back to top</a>
        <div class="flexbox-item-buttons">
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
            <button class="button-type"
                :class="{
                    'active': carType == 'next'
                }"
                @click="changeResult('next')">
                &rsaquo;
            </button>

            <button class="button-type"
                :class="{
                    'active': carType == 'end'
                }"
                @click="changeResult('end')">
                &rsaquo;&rsaquo;
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

<style scoped lang="scss">
@import '~/assets/css/main.scss';

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
    color: $text-grey-color;
}

.button-type {
    padding: 2px 25px 2px 25px;
    border-radius: 12px;
    cursor: pointer;
    margin-right: 5px;
    color: $text-grey-color;
    border: solid 1px $border-grey-color;
    background-color: #FFFFFF;
}

.active {
    color: #FFFFFF;
    background-color: $primary-color;
    border: solid 1px $primary-color;
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