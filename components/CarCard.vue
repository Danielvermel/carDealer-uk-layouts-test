<template>

    <article class="card">
        <img class="card-img-top" :src="imagePath.medium" alt="Card image cap">
        <span class="card-classification">{{capitalize(carInfo.advert_classification)}}</span>
     
    <div class="card-body">
        <div class="flexbox-container">
            <h5 class="card-title">{{carInfo.plate}} {{carInfo.make}}</h5>
             <StarOutlineIcon  v-if="!favouriteCar" class="star-icon" @click="favouriteCar = !favouriteCar" />
             <StarIcon v-else class="star-icon" @click="favouriteCar = !favouriteCar" />
        </div>
        
        <p class="card-text">{{carInfo.model}}</p>
        <p><strong>£{{carInfo.price_mo}}</strong> / mo (PCP)</p>
        <p class="card-text-finance">
            <span class="text-muted">£{{carInfo.original_price.split('.')[0].replace(/\B(?=(\d{3})+(?!\d))/g, ",")}}</span> 
            <span class="card-body-finance">Calculate finance</span></p>
    </div>
    </article>


</template>



<script>
import StarOutlineIcon from 'vue-material-design-icons/StarOutline.vue';
import StarIcon from 'vue-material-design-icons/Star.vue';
export default {
    props: ['imagePath', 'carInfo' ],
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
      capitalize: function(word){
          return word.toLowerCase().charAt(0).toUpperCase() + word.toLowerCase().slice(1)
      }
  }

}
</script>

<style scoped>

.card{
    box-shadow: 0px 0px 20px 0px lightgrey;
    position: relative;
}

.card-classification{
    top: 10px;
    left: 10px;
    padding: 1px 10px 1px 10px;
    border-radius: 8px;
    position: absolute;
    color: #FFFFFF;
    background-color: #3F3A50;
    border: 1px solid rgba(255, 255, 255, .2);
}

.card-img-top {
    border-radius: 20px 20px 0 0;
    height: 250px;
}

.card-text-finance{
    font-size: 12px;
}

.card-body-finance{
    color: #7572FF;
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