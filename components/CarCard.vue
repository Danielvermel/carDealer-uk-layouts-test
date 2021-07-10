<template>

    <article class="card">
        <div v-if="$vnode.key !== 4">
            <div class="card-img-text-container">
                <img class="card-img-top" :src="carInfo.media" alt="Card image cap">
                <CardClassification :classification="carInfo.advert_classification" />
                <div class="card-specs-list"> 
                    <CardSpec :specs="carInfo.fuel_type"/>
                    <CardSpec :specs="carInfo.body_type"/>
                </div>
            </div>
        
            <div class="card-body">
                <div class="flexbox-container">
                    <p class="card-title">{{carInfo.plate}} {{carInfo.make}}</p>
                    <StarOutlineIcon  v-if="!favouriteCar" class="star-icon" @click="favouriteCar = !favouriteCar" />
                    <StarIcon v-else class="star-icon" @click="favouriteCar = !favouriteCar" />
                </div>
                
                <caption>{{carInfo.model}}</caption>
               

                <div class="card-finance-container">
                    <span class="card-monthly-price"><strong>£{{carInfo.price_mo}}</strong> / mo (PCP)</span>
                    <br>
                    <span class="card-finance-text"
                        :class="{
                            'card-price-reduced' : carInfo.reduced_price
                        }">
                        £{{carInfo.reduced_price ? priceFixer(carInfo.reduced_price) : priceFixer(carInfo.original_price)}}
                    </span> 
                    <del v-if="carInfo.reduced_price" class="card-finance-text">£{{priceFixer(carInfo.original_price)}} </del>
                    <span class="card-finance-calculate">Calculate finance</span>
                </div>
            </div>
        </div>

        <div v-else class="card-valuation">
            <div class="card-valuation-container">
                <h3>Value your car</h3>
                <p>Find out the value of your car in just a few minutes.</p>
                <CardValuationInput inputLable="VRM"/>
                <CardValuationInput inputLable="Mileage"/>
            
                <span class="card-valuation-button">Value my car</span>
            </div>
        </div>
    </article>


</template>



<script>
import StarOutlineIcon from 'vue-material-design-icons/StarOutline.vue';
import StarIcon from 'vue-material-design-icons/Star.vue';
export default {
    props: ['carInfo'],
    components: {
        StarOutlineIcon,
        StarIcon
    },
    data() {
        return {
            favouriteCar: false,
        };
    },
    methods: {
        priceFixer: function(value){
            return value.split('.')[0].replace(/\B(?=(\d{3})+(?!\d))/g, ",")
        }
    }
}
</script>

<style scoped>

.card{
    box-shadow: 0px 0px 20px 0px lightgrey;
    height: 364;
}

.card-img-text-container{
    position: relative
}

.card-valuation{
    background-color: #F6F7FB;
    height: 100%;
    border-radius: 16px;
}

.card-valuation-container {
    margin: 30px 30px;
    display: flex;
    flex-direction: column;
    text-align: center;
}

.card-valuation-button{
    color: #FFFFFF;
    background-color: #7572FF;
    padding: 11px 25px 12px 25px;
    border-radius: 16px;
}

.card-img-top {
    border-radius: 16px 16px 0 0;
    height: 250px !important;
    position: relative;
}

.card-body {
    height: 115px;
    padding: 10px;
}

.card-specs-list{
    display: flex;
    flex-wrap: wrap;
    justify-content: start;
    position: absolute;
    bottom: 10px;
}

.card-title{
    margin-bottom: 0;
    font-size: 16px;
}

caption {
    display: flex;
    padding: 0;
    font-size: 12px;
}

.card-finance-container{
    margin-top: 10px;
}

.card-monthly-price{
    font-size: 12px;
}

.card-finance-text{
    font-size: 12px;
}

.card-price-reduced{
    color: #F87B7B;
}

del {
    color: #55595D;
}

.card-finance-calculate{
    color: #7572FF;
    margin-left: 8px;
    font-size: 12px;
}

.flexbox-container{
    display: flex;
    justify-content: space-between;
}

.star-icon{
    color: #7572FF;
    cursor: pointer;
}
</style>