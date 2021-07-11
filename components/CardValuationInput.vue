<template>
    <div class="card-validation-input-container">
        <div class="card-validation-input-text">
            {{inputLable}} 
            <span class="card-validation-input-text-required">*</span>
        </div>
        <input type="text" class="card-valuation-input" :placeholder="'  Enter ' + inputLable"/>
    </div>
</template>



<script>
export default {
    props: ['inputLable'],
}
</script>


<style scoped lang="scss">
@import '~/assets/css/main.scss';

.card-valuation-input{
    border-radius: $border-radius-lg;
    border: solid 1px #FFFFFF;
    height: 50px;
    margin-bottom: 15px;
    width:100%
}

.card-validation-input-container{
    position: relative;
}

.card-validation-input-text{
    color: black;
    background-color: $background-white-color;
    display: block;
    position: absolute;
    border-radius: 100px;
    padding: 0px 6px 0px 6px;
    top: -9px
}

.card-validation-input-text-required{
    color: #F87B7B;
}

</style>