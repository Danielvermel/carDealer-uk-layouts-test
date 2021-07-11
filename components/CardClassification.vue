<template>
    <span class="card-classification text-white">
        {{capitalize(classification)}}
    </span>
</template>


<script>
export default {
    props: ['classification'],
    methods: {
        capitalize: function(word){
            return word.toLowerCase().charAt(0).toUpperCase() + word.toLowerCase().slice(1)
        }
    }
}
</script>

<style scoped lang="scss">
@import '~/assets/css/main.scss';

.card-classification{
    top: 10px;
    left: 10px;
    padding: 1px 10px 1px 10px;
    font-weight: 600;
    font-size: 16px;
    border-radius: $border-radius-sm;
    position: absolute;
    background-color: #3F3A50;
    border: 1px solid rgba(255, 255, 255, .2);
    font-family: 'Overpass', sans-serif;
}

</style>