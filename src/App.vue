<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import Mybar from "./components/Mybar.vue";
import Mycard from "./components/Mycard.vue";
// import items from "./attractions.json";
</script>

<template>
  <header>
    <Mybar />
  </header>

  <main>
    <h1 style="padding-left: 10px">Attractions</h1>
    <div class="grid-container">
      <!-- <Mycard v-for="item in items" v-bind="item"/> -->
      <!-- <Mycard v-for="todo in items" :key="todo" v-bind="todo" /> -->
      <Mycard v-for="item in items" v-bind:key="item.id" v-bind="item" />
    </div>
  </main>
</template>
<script>
export default {
  data() {
    return {
      items: []
    }
  },
  created() {
    fetch('https://www.melivecode.com/api/attractions')
    .then(res => res.json())
    .then((result) => {
      this.items = result
    })
  }
}
</script>
<style scoped>
.grid-container {
  display: grid;
  grid-column-gap: 0.5rem;
  grid-row-gap: 0.5rem;
}

@media (min-width: 576px) {
  .grid-container {
    grid-template-columns: repeat(1, 1fr);
  }
}
@media (min-width: 992px) {
  .grid-container {
    grid-template-columns: repeat(3, 1fr);
  }
}
@media only screen and (min-width: 1200px) {
  .grid-container {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
