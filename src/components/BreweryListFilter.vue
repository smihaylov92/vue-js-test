<template>
  <section class="filter">
    <select v-model="selectedType" @change="selectType">
      <option :value="''">all</option>
      <option v-for="(type, index) in breweryTypes" :key="index">{{ type }}</option>
    </select>
  </section>
</template>

<script>
import { EventBus } from '../modules/eventbus.js';

export default {
  data() {
    return {
      breweryTypes: ['micro', 'contract', 'brewpub', 'regional'],
      selectedType: ''
    };
  },
  methods: {
    selectType: function() {
      EventBus.$emit("type", this.selectedType);
    }
  }
}
</script>

<style scoped>
select {
  padding: 12px;
  font-size: 1rem;
  margin-bottom: 24px;
}
</style>
