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
          link: "http://www.cats.com",
          visible: true,
          color: "red",
          background: "gray",
          image: "https://images.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg",
        },
        {
          id: 2,
          title: "Big Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          color: "blue",
          image: "https://d3544la1u8djza.cloudfront.net/APHI/Blog/2016/10_October/Do+Cats+Get+Pink+Eye+_+ASPCA+Pet+Health+Insurance+_+orange+tabby+cat+with+green+eyes-min.jpg",
        },
        {
          id: 3,
          title: "Bigger Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          color: "yellow",
          background: "green",
          image: "https://media-cldnry.s-nbcnews.com/image/upload/t_fit-760w,f_auto,q_auto:best/rockcms/2022-08/220805-domestic-cat-mjf-1540-382ba2.jpg",
        },
        {
          id: 4,
          title: "Biggest Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: false,
          color: "purple",
          image: "https://i.pinimg.com/474x/2c/8d/47/2c8d47ae73ff9469c50503c1b3dd3d33--largest-domestic-cat-cat-face.jpg",
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
