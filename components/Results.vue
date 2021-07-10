<template>
  <div class="">
      <TopContent />
      <div class="flexbox-container"> 
        <CarCard
            v-for="carInfo,index in carsData"
            :key="index"
            :carInfo="carInfo"
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
          this.carsData = response.data.cars
          console.log(response.data.cars)
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
}

.flexbox-item {
    width: 333px;
    margin: 0 5px 20px 5px;
    border-radius: 20px;
}

</style>