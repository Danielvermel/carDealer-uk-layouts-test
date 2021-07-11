<template> 
    <aside class="d-none-tablet">
        <div class="mx-3">
             <div class="flexbox-container justify-content-between my-5 filters-header">
            <strong>Filters</strong> 
            <button class="button-reset">Reset</button>
        </div>
        <div>
            <span class="filter-titles text-disabled">Brand</span>
            <ul class="mb-3">
                <FilterOption
                    v-for="data,index in filterOptions.brand"
                    :key="index"
                    :option="data"
                />
            </ul>

            <span class="filter-titles text-disabled">Specification</span>
            <ul class="mb-3">
                 <FilterOption
                    v-for="data,index in filterOptions.specifications"
                    :key="index"
                    :option="data"
                />
            </ul>
        </div>
        </div>
       
    </aside>

</template>


<script>

export default {
  data() {
    return {
        filterOptions: {
            brand: [
                'Make',
                'Model'
            ],

            specifications: [
                'Fuel type',
                'Body type',
                'Transmission',
                'Engine size',
                'Mileage',
                'Colour',
                'Doors',
                'Seats',
                'Features'
            ]
        },
        
    };
  },
}
</script>

<style scoped lang="scss">
@import '~/assets/css/main.scss';

.filters-header{
    height: 46px;
    align-items: center;
}

.button-reset {
    color: #F87B7B;
    background-color: rgb(248 123 123 / 15%);
    border-radius: $border-radius-lg;
    padding: 6px 7px;
    border: none;
}

.filter-titles {
    text-transform: uppercase;
    font-family: 'Overpass', sans-serif;
    font-size: 12px;
}
ul {
    list-style-position: inside;
    padding-left: 0;
    display:grid;

}

</style>