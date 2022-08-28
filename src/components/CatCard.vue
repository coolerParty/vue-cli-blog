<template>
  <div class="catCart" :style="{
    background: cat.background
  }">
    <div v-if="cat.visible == true">
      <h2>{{ cat.id }}</h2>
      <h1
        :style="{
        color: cat.color
      }"
      >
        {{ cat.title }}
      </h1>
      <p>{{ cat.msg }}</p>
      <a :href="cat.link">{{ cat.link }}</a>
    </div>
    <div v-else-if="cat.id == 3">
      <h2>{{ cat.id }}</h2>
      <h1>{{ cat.title }}</h1>
    </div>
    <div v-else :style="{
        color: cat.color
      }">
      <strong>{{ cat.id }} This is not available.</strong>
    </div>
  </div>
</template>

<script>
export default {
  name: "CatCard",
  props: {
    cat: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.catCart {
  display: inline-flex;
  border: 1px solid #e6e6e6;
  width: 300px;
  height: 300px;
  justify-content: center;
}
</style>
