<template>

    <article class="card">
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
            <h5 class="card-title">{{carInfo.plate}} {{carInfo.make}}</h5>
             <StarOutlineIcon  v-if="!favouriteCar" class="star-icon" @click="favouriteCar = !favouriteCar" />
             <StarIcon v-else class="star-icon" @click="favouriteCar = !favouriteCar" />
        </div>
        
        <p class="card-text">{{carInfo.model}}</p>
        <p><strong>£{{carInfo.price_mo}}</strong> / mo (PCP)</p>
        <p class="card-text-finance">
            <span class=""
                :class="{
                    'card-price-reduced' : carInfo.reduced_price
                }">£{{carInfo.reduced_price ? priceFixer(carInfo.reduced_price) : priceFixer(carInfo.original_price)}}</span> 
            <del v-if="carInfo.reduced_price">£{{priceFixer(carInfo.original_price)}} </del>
            <span class="card-body-finance">Calculate finance</span>
        </p>
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
    mounted(){
        console.log(this.carInfo)
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
}

.card-img-text-container{
    position: relative
}

.card-img-top {
    border-radius: 20px 20px 0 0;
    height: 250px;
    position: relative;
}
.card-specs-list{
    display: flex;
    flex-wrap: wrap;
    justify-content: start;
    position: absolute;
    bottom: 10px;
}

.card-text-finance{
    font-size: 12px;
}

.card-price-reduced{
    color: #F87B7B;
}

del {
    color: #55595D;
}

.card-body-finance{
    color: #7572FF;
    margin-left: 8px;
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