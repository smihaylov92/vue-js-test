<template>
  <div class="home">
    <h1>Breweries</h1>

    <div class="card-wrapper">
      <card
        v-for="brewery in breweries"
        :key="brewery.id"
        :brewery="brewery"
      ></card>
    </div>
  </div>
</template>
<script>
import axios from "axios";
import Card from "./Card/Card";

export default {
  components: {
    Card,
  },
  data() {
    return {
      breweries: [],
    };
  },
  created() {
    this.getBreweries();
  },
  methods: {
    async getBreweries() {
      const { data } = await axios.get(
        "https://api.openbrewerydb.org/breweries"
      );

      this.breweries = data;
    },
  },
};
</script>

<style scoped>
.home {
  width: 100%;
}

h1 {
  width: 100%;
}
.card-wrapper {
  display: flex;
  width: 80%;
  justify-content: flex-start;
  flex-wrap: wrap;
  margin: auto;
  padding: 5px;
}
.card-wrapper > * {
  flex: 0 0 calc(50% - 10px);
  margin: 5px;
}
</style>
