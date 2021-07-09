<template>
  <div class="">
      <TopContent />
      <div class="row"> 
        <CarCard
            v-for="carMedia,index in carsData.media_urls"
            :key="index"
            :imagePath="carMedia"
            :carInfo="carsData"
            class="col-md-4 mx-2 my-3" 
       />
      </div>


  </div>
</template>
<script>

import axios from 'axios';
export default {
  data() {
    return {
        carsData: {}
    };
  },
  mounted() {   
    this.fetchData();
  },
  methods: {
    async fetchData() {
      axios.get('/data.json')
        .then((response) => {
          console.log(response.data.advert_classification)
          this.carsData = response.data
          console.log(this.carsData)
        })
        .catch(response => { this._failed(response); });   
    },
  },
};
</script>
