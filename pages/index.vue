<template>
    <body>
      <FinanceBanner />
      <div class="flexbox-container">
        <aside class="flexbox-item-filter"> 
          <FilterCars />
        </aside>
        <section class="flexbox-item-results">
          <Results />
        </section>
      </div>
    </body>
</template>

<style scoped> 

.flexbox-container {
  display: flex;
  flex-wrap: wrap;
}
.flexbox-item-filter{
  width: 25%
}

.flexbox-item-results {
  width: 75%
}

</style>