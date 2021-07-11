<template>

    <article v-if="advertClassification =='all' || advertClassification == carInfo.advert_classification.toLowerCase() || advertClassification == offerAdvert">
        <div class="card m-1">
            <div class="" v-if="$vnode.key !== 4">
                <div 
                    v-for="image, index in carInfo.media" 
                    :key="index"
                    class="card-img">
                    <div v-if="index < 1">
                        <img :src="image" alt="car">
                        <CardClassification :classification="carInfo.advert_classification" />
                        <CardCarouselNav v-if="carInfo.media.length > 1" :i="index +1" :amount="carInfo.media.length"/>
                        <div class="card-specs-list"> 
                            <CardSpec :specs="carInfo.fuel_type"/>
                            <CardSpec :specs="carInfo.body_type"/>
                        </div>
                    </div>
                </div>
            
                <div class="card-body p-2">
                    <div class="flexbox-container justify-content-between">
                        <span class="card-title mb-0">{{carInfo.plate}} {{carInfo.make}}</span>
                        <StarOutlineIcon  v-if="!favouriteCar" class="star-icon" @click="favouriteCar = !favouriteCar" />
                        <StarIcon v-else class="star-icon" @click="favouriteCar = !favouriteCar" />
                    </div>
                    
                    <caption class="text-disabled">{{carInfo.model}}</caption>             

                    <div class="mt-3">
                        <span class="card-monthly-price"><strong>£{{carInfo.price_mo}}</strong> / mo (PCP)</span>
                        <span class="card-finance-text"
                            :class="{
                                'card-price-reduced' : carInfo.reduced_price
                            }">
                            £{{carInfo.reduced_price ? priceFixer(carInfo.reduced_price) : priceFixer(carInfo.original_price)}}
                        </span> 
                        <del v-if="carInfo.reduced_price">£{{priceFixer(carInfo.original_price)}} </del>
                        <span class="card-finance-calculate ml-1">Calculate finance</span>
                    </div>
                </div>
            </div>

            <div v-else class="card-valuation">
                <div class="card-valuation-container m-4">
                    <h3>Value your car</h3>
                    <p class="card-valuation-text my-2">Find out the value of your car in just a few minutes.</p>
                    <div class="mt-4 mb-3">
                        <CardValuationInput inputLable="VRM"/>
                        <CardValuationInput inputLable="Mileage"/>
                    </div>
                    
                    <button class="card-valuation-button">Value my car</button>
                </div>
            </div>
        </div>
    </article>

</template>

<script>
import StarOutlineIcon from 'vue-material-design-icons/StarOutline.vue';
import StarIcon from 'vue-material-design-icons/Star.vue';
export default {
    props: ['carInfo', 'advertClassification', 'offerAdvert'],
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

<style scoped lang="scss">
@import '~/assets/css/main.scss';

article {

    .card {
        box-shadow: 0px 0px 20px 0px lightgrey;
        position:relative;
        display:-ms-flexbox;
        display:flex;
        -ms-flex-direction:column;
        flex-direction:column;
        min-width:0;
        word-wrap:break-word;
        background-color:#fff;
        background-clip:border-box;
        border:1px solid rgba(0,0,0,.125);
        border-radius: $border-radius-lg;

   
        .card-img {
            position: relative;

            img {
                -ms-flex-negative:0;
                flex-shrink:0;
                width: 100%;
                border-radius: $border-radius-lg $border-radius-lg 0 0;
                height: 250px !important;
                position: relative;
            }

            .card-specs-list{
                display: flex;
                flex-wrap: wrap;
                justify-content: start;
                position: absolute;
                bottom: 10px;
            }
        }

        .card-body{
            -ms-flex:1 1 auto;
            flex:1 1 auto;
            min-height:1px;
            height: 115px;

            .card-title{
                font-size: 16px;
            }

            .star-icon{
                color: $primary-color;
                cursor: pointer;
            }

            caption {
                display: flex;
                padding: 0;
                font-size: 12px;
                line-height: 5px
            }

            .card-monthly-price{
                font-size: 12px;
                display: block;
                font-family: 'Overpass', sans-serif;

                strong {
                    font-size: 18px;
                }
            }

            .card-finance-text{
                font-size: 12px;
                display: inline-block;
                line-height:0px;
            }

            .card-price-reduced{
                color: #F87B7B;
                display: inline-block
            }

            del {
                color: $text-grey-color;
                font-size: 12px;
            }

            .card-finance-calculate{
                color: $primary-color;
                font-size: 12px;
            }
        }

        .card-valuation{
            background-color: $background-white-color;
            height: 100%;
            border-radius: $border-radius-lg;
    
            .card-valuation-container {
                display: flex;
                flex-direction: column;
                text-align: center;

                h3 {
                    font-family: 'Overpass', sans-serif;
                    font-size: 24px;
                    font-weight: 600;
                }

                p{
                    width: 100%;
                    line-height: 24px;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
                    font-weight: 400;
                }

                button {
                    color: #FFFFFF;
                    background-color: $primary-color;
                    padding: 11px 25px 12px 25px;
                    border-radius: $border-radius-lg;
                    border: none;
                    font-size: 16px;
                    font-family: 'Overpass', sans-serif;
                }
            }
        }
    }
}
</style>