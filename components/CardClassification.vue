<template>
    <span class="card-classification">
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


<style scoped>
.card-classification{
    top: 10px;
    left: 10px;
    padding: 1px 10px 1px 10px;
    font-weight: 600;
    font-size: 16px;
    border-radius: 8px;
    position: absolute;
    color: #FFFFFF;
    background-color: #3F3A50;
    border: 1px solid rgba(255, 255, 255, .2);
}

</style>