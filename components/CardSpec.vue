<template>
    <span class="card-specs">
        {{capitalize(specs)}}
    </span>
</template>


<script>
export default {
    props: ['specs'],
    methods: {
        capitalize: function(word){
            return word.toLowerCase().charAt(0).toUpperCase() + word.toLowerCase().slice(1)
        }
    }
}
</script>


<style scoped lang="scss">
@import '~/assets/css/main.scss';

.card-specs{
    font-size: 12px;
    bottom: 10px;
    margin-left: 10px;
    padding: 1px 10px 1px 10px;
    border-radius: $border-radius-sm;
    color: #FFFFFF;
    background-color: #3F3A50;
    border: 1px solid rgba(255, 255, 255, .2);
}

</style>