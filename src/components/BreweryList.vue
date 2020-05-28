<template>
  <div>
    <!-- BreweryListFilter -->

    <section class="breweries">
      <div class="brewery-item">
        <!-- BreweryListItem -->
      </div>
    </section>
  </div>
</template>

<script>

export default {
 
};
</script>

<style scoped>
.breweries {
  display: grid;
  column-gap: 24px;
  row-gap: 24px;
  justify-items: stretch;
  grid-template: repeat(3, 1fr) ;
  grid-template-columns: 1fr 1fr 1fr;
  max-width: 900px;
  margin: 0 auto;
}
</style>