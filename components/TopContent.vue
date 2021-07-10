<template>
    <header>

    <div class="flex-container">
        <span class="car-quantaty-text">Showing {{carQuantity}} cars</span>
        <span class="button-type"
            :class="{
                'active': carType == 'all'
            }"
            @click="changeResult('all')">
            All
        </span>
            <span class="button-type"
            :class="{
                'active': carType == 'used'
            }"
            @click="changeResult('used')">
            Used
        </span>
        <span class="button-type"
            :class="{
                'active': carType == 'new'
            }"
            @click="changeResult('new')">
            New
        </span>
        <span class="button-type"
            :class="{
                'active': carType == 'offers'
            }"
            @click="changeResult('offers')">
            Offers
        </span>
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

header {
    margin: 40px 0;
}

.flexbox-container {
    display: flex;
}

.button-type {
    padding: 8px 25px 8px 25px;
    border-radius: 12px;
    cursor: pointer;
    margin-right: 5px;
    color: #55595D;
    border: solid 1px #D1D6E0
}

.active {
    color: #FFFFFF;
    background-color: #7572FF;
    border: none;
}

.car-quantaty-text{
    font-weight: 700;
    font-size: 18px;
    margin-right: 30px;
}

</style>