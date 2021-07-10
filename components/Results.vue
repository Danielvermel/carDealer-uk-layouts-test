<template>
  <section>
      <TopContent  
        :carQuantity="carsData.length"
        @classificationData="classification"
    />
      <div class="flexbox-container"> 
        <CarCard
            v-for="carInfo,index in carsData"
            :key="index"
            :advertClassification="advertClassification"
            :offerAdvert="carInfo.reduced_price ? 'offers' : ''"
            :carInfo="carInfo"
            class="flexbox-item" 
       />
      </div>
      <BottomContent />
      <RepresentativeContent />
  </section>
</template>
<script>

import axios from 'axios';
export default {
  data() {
    return {
        carsData: {},
        advertClassification: 'all'
    };
  },
  mounted() {   
    this.fetchData();
  },
  methods: {
    async fetchData() {
      axios.get('/data.json')
        .then((response) => {
          this.carsData = response.data.cars
          console.log(response.data.cars)
        })
        .catch(response => { this._failed(response); });   
    },

    classification(value){
        console.log(value)
        this.advertClassification = value;


    }
  },
};
</script>

<style scoped>
.flexbox-container{
    display: flex;
    flex-wrap: wrap;
}

.flexbox-item {
    width: 333px;
    margin: 0 5px 20px 5px;
    border-radius: 16px;
}

</style>