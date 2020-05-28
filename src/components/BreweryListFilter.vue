<template>
  <section class="filter">
    <select @change="$emit('input', $event.target.value)">
      <option v-for="(type, index) in breweryTypes" :key="index" :value="type">{{ type }}</option>
    </select>
  </section>
</template>

<script>
export default {
  data() {
    return {
      breweryTypes: ['', 'micro', 'contract', 'brewpub', 'regional'],
    };
  },
}
</script>

<style scoped>
select {
  padding: 12px;
  font-size: 1rem;
  margin-bottom: 24px;
}
</style>
