<template>
  <a class="card">
    <h1></h1>
    <p>Type: </p>
    <main>
      <p>Country: </p>
      <p>City: </p>
      <p>State: </p>
      <p>Street: </p>
    </main>
    <footer>
      <button>
        <span>
          Show Info
        </span>
      </button>
    </footer>
  </a>
  <!-- <a :href="brewery.website_url" class="card">
    <h1>{{brewery.name}}</h1>
    <p>Type: {{brewery.brewery_type}}</p>
    <main v-if="isInfoShown">
      <p>Country: {{ brewery.country }}</p>
      <p>City: {{ brewery.city }}</p>
      <p>State: {{ brewery.state }}</p>
      <p>Street: {{ brewery.street }}</p>
    </main>
    <footer>
      <button @click.prevent="isInfoShown = !isInfoShown" :class="{ active: isInfoShown }">
        <span v-if="!isInfoShown">
          Show Info
        </span>
        <span v-else>
          Hide Info
        </span>
      </button>
    </footer>
  </a> -->
</template>

<script>
export default {
  // props: {
  //   brewery: {
  //     type: Object,
  //     default: null
  //   }
  // },
  // data() {
  //   return {
  //     isInfoShown: false
  //   }
  // }
};
</script>

<style scoped>
.card {
  border: 1px solid #f0f0f0;
  border-radius: 6px;
  padding: 12px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-decoration: none;
}

h1 {
  font-size: 1.2rem;
}

h1,
p {
  color: rgba(0, 0, 0, 0.87);
}

button {
  width: 100%;
  text-align: center;
  padding: 12px;
  border: 1px solid #f3f3f3;
  cursor: pointer;
  text-transform: uppercase;
  font-weight: bold;
  color: #fff;
  background: #61b049;
}

.active {
  background: red;
}
</style>
