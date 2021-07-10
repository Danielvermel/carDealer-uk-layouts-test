<template>
  <div class="">
      <TopContent />
      <div class="flexbox-container"> 
        <CarCard
            v-for="carMedia,index in carsData.media_urls"
            :key="index"
            :imagePath="carMedia"
            :carInfo="carsData"
            class="flexbox-item" 
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

<style scoped>
.flexbox-container{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.flexbox-item {
    width: 333px;
    margin: 0 5px 20px 5px;
    border-radius: 20px;
}

</style>