<template>
    <li class="mt-4">
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
        margin-left: 10px;

        .plus-icon {
            border-radius: 8px;
            border: 1px solid $border-grey-color;
            color: $border-grey-color;
            padding: 0 6px;
        }
    }
</style>