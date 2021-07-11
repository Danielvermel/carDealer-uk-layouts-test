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


    li {
        margin-left: 10px;

        .plus-icon {
            border-radius: 8px;
            border: 1px solid #D1D6E0;
            color: #D1D6E0;
            padding: 0 6px;
        }
    }
</style>