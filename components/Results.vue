<template>
  <section>
      <div class="mr-3">
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
              class="flexbox-item-lg-4 flexbox-item-md-6 flexbox-item-sm-12 p-1" 
        />
        </div>
        <BottomContent/>
        <RepresentativeContent/>
      </div>

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
        })
        .catch(response => { this._failed(response); });   
    },

    classification(value){
        this.advertClassification = value;
    }
  },
};
</script>

<style scpoed lang="scss">
@import '~/assets/css/main.scss';
</style>