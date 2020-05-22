<template>
  <div class="card">{{brewery.name}}
    <button>Details</button>
  </div>
  
</template>
<script>
export default {
  props: {
    brewery: {
      type: Object,
      default: null
    }
  }
};
</script>
<style scoped>
.card {
  height: 300px;
  border: 1px solid #f0f0f0;
  padding: 5px;
  display: flex;
  flex-direction: column;
}

button {
  width: 100px;
  height: 50px;
  border: 1px solid #f3f3f3;
  background-color: #ffffff;
}
</style>
