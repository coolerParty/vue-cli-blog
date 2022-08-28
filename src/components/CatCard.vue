<template>
  <a :href="cat.link">
    <div :class="[cat.visible ? 'visible' : 'invisible', 'catCard']">
      <div v-if="cat.visible == true">
      <img :src="cat.image" alt="" class="catImage">
        <h1>
          {{ cat.title }}
        </h1>
        <p>{{ cat.msg }}</p>
        <a :href="cat.link" target="_blank">{{ cat.link }}</a>
      </div>
      <div v-else-if="cat.id == 3">
        <img :src="cat.image" alt="" class="catImage">
        <h1>{{ cat.title }}</h1>
      </div>
      <div v-else>
        <strong>{{ cat.id }} This is not available.</strong>
      </div>
    </div>
  </a>
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
  a {
    text-decoration: none;
    color: white;
  }
.catCard {
  display: inline-flex;
  border: 1px solid #e6e6e6;
  width: 300px;
  height: 300px;
  justify-content: center;
}
.visible {
  background: green;
}
.invisible {
  background: grey;
}
.catImage{
  width: 100%;
  height: 100px;
  object-fit: cover;
}
</style>
