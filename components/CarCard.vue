<template>

<div class="card">
  <img class="card-img-top" :src="imagePath.medium" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{carInfo.plate}} {{carInfo.make}}</h5>
    <p class="card-text">{{carInfo.model}}</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>


</template>

<script>
export default {
    props: ['imagePath', 'carInfo' ],

}
</script>
