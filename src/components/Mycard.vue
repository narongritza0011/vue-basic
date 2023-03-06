<template lang="">
  <div>
    <div class="card">
      <img :src="coverimage" :alt="name" style="width: 100%" />
      <div className="container">
        <h3>
          <b>{{ name }}</b>
        </h3>
        <p>
          {{ detail }}
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["id", "name", "detail", "coverimage"],
};
</script>
<style scoped>
.card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  padding-bottom: 10px;
}
/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}
</style>
