<template>
    <li class="mt-4 ml-2">
        <span class="option-text">{{option}}</span> 
        <span class="plus-icon">+</span>
    </li>
</template>


<script>
export default {
    props: ['option']

}
</script>

<style scoped lang="scss">
@import '~/assets/css/main.scss';

    li {
        .option-text {
            float: left;
            font-size: 16px;
            font-weight: 400;
        }

        .plus-icon {
            border-radius: $border-radius-sm;
            border: 1px solid $border-grey-color;
            color: $border-grey-color;
            padding: 0 6px;
            float: right;
        }
    }
</style>