<template>
  <div class="CatCard">
    <h1>{{ title }}</h1>
    <p>{{ msg }}</p>
    <a :href="link">{{ link }}</a>
  </div>
</template>

<script>
export default {
  name: "CatCard",  
  props: {
    msg: String,
    title: String,
    link: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
