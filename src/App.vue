<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <cat-card
      v-for="item in listOfCats"
      v-bind:key="item.id"
      :title="item.title"
      :msg="item.msg"
      :link="item.link"
    />
  </div>
</template>

<script>
import CatCard from "./components/CatCard.vue";

export default {
  name: "App",
  data: function () {
    return {
      listOfCats: [
        {
          id: 1,
          title: "Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
        },
        {
          id: 2,
          title: "Big Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
        },
        {
          id: 3,
          title: "Bigger Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
        },
      ],
    };
  },
  components: {
    CatCard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
