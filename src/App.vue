<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <br>
    <cat-card
      v-for="item in listOfCats"
      v-bind:key="item.id"
      :cat="item"
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
          visible: true,
          color: "red",
          background: "gray"
        },
        {
          id: 2,
          title: "Big Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
          visible: true,
          color: "blue",
        },
        {
          id: 3,
          title: "Bigger Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
          visible: false,
          color: "yellow",
          background: "green"
        },
        {
          id: 4,
          title: "Biggest Cats",
          msg: "Welcome to Your Vue.js App",
          link: "www.cats.com",
          visible: false,
          color: "purple",
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
