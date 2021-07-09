<template>
  <Tutorial/>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      profile: {},
      education: [],
      careers: [],
      projects: [],
      contacts: {},
    };
  },
  mounted() {   
    this.fetchData();
  },
  methods: {
    async fetchData() {
      let data
      const dataPath = '/data.json'; 
      axios.get('/data.json')
        .then((response) => {
          console.log(response.data)
        })
        .catch(response => { this._failed(response); });   
    },
  },
};
</script>
