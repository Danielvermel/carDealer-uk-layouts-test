<template>
    <li class="mt-4 ml-2">
        <span class="float-left">{{option}}</span> 
        <span class="float-right plus-icon">+</span>
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
        .plus-icon {
            border-radius: $border-radius-sm;
            border: 1px solid $border-grey-color;
            color: $border-grey-color;
            padding: 0 6px;
        }
    }
</style>