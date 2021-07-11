<template>

    <article v-if="advertClassification =='all' || advertClassification == carInfo.advert_classification.toLowerCase() || advertClassification == offerAdvert">
        <div v-if="$vnode.key !== 4">
            <div class="ccard-img">
                <img :src="carInfo.media" alt="car">
                <CardClassification :classification="carInfo.advert_classification" />
                <div class="card-specs-list"> 
                    <CardSpec :specs="carInfo.fuel_type"/>
                    <CardSpec :specs="carInfo.body_type"/>
                </div>
            </div>
        
            <div class="ccard-body">
                <div class="flexbox-container justify-content-between">
                    <p class="card-title mb-0">{{carInfo.plate}} {{carInfo.make}}</p>
                    <StarOutlineIcon  v-if="!favouriteCar" class="star-icon" @click="favouriteCar = !favouriteCar" />
                    <StarIcon v-else class="star-icon" @click="favouriteCar = !favouriteCar" />
                </div>
                
                <caption>{{carInfo.model}}</caption>
               

                <div class="mt-2">
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
                <p class="card-valuation-text">Find out the value of your car in just a few minutes.</p>
                <div class="my-3">
                    <CardValuationInput inputLable="VRM"/>
                    <CardValuationInput inputLable="Mileage"/>
                </div>
                
                <button class="card-valuation-button">Value my car</button>
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
    box-shadow: 0px 0px 20px 0px lightgrey;
    height: 364;
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

    .ccard-img {
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

    .ccard-body{
        -ms-flex:1 1 auto;
        flex:1 1 auto;
        min-height:1px;
        padding:1.25rem;
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
        }

        .card-monthly-price{
            font-size: 12px;
            display: block;
        }

        .card-finance-text{
            font-size: 12px;
            display: inline-block
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
            }

            p{
                width: 100%;
            }

            button {
                color: #FFFFFF;
                background-color: $primary-color;
                padding: 11px 25px 12px 25px;
                border-radius: $border-radius-lg;
                border: none;
            }
        }
    }
}
</style>