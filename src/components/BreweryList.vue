<template>
  <div>
    <BreweryListFilter/>

    <div>
      Number of results: {{ filteredBreweries.length }}
    </div>
    <section class="breweries">
      <div class="brewery-item" v-for="brewery in filteredBreweries" :key="brewery.id">
        <BreweryListItem
          :brewery="brewery"
        />
      </div>
    </section>
  </div>
</template>

<script>

import axios from "axios";
import { EventBus } from '../modules/eventbus.js';
import BreweryListItem from "./BreweryListItem";
import BreweryListFilter from "./BreweryListFilter";

export default {
  components: {
    BreweryListItem,
    BreweryListFilter
  },
  data() {
    return {
      breweries: [],
      type: ''
    };
  },
  computed: {
    filteredBreweries() {
      return this.breweries.filter((brewery) => {
        return brewery.brewery_type.toLowerCase().indexOf(this.type.toLowerCase()) > -1
      });
    }
  },
  methods: {
    async getBreweries() {
      const { data } = await axios.get(
        "https://api.openbrewerydb.org/breweries"
      );

      this.breweries = data;
    },

    getSelectedType() {
      EventBus.$on("type", selectedType => {
        this.type = selectedType;
      });
    },
  },
  created() {
    this.getBreweries();
    this.getSelectedType();
  },
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