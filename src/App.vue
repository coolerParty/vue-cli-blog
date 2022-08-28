<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <br />
    <div class="newCat">
      <h3>Add a Cat</h3>
      <div><span>Title: </span> <input type="text" v-model="newCat.title" /></div>
      <div><span>Message: </span> <input type="text" v-model="newCat.msg" /></div>
      <div><span>Link: </span> <input type="text" v-model="newCat.link" /></div>
      <div><span>Image URL: </span> <input type="text" v-model="newCat.image" /></div>
      <br />
      <button type="submit" @click="addCat()">Add Cat</button>
      <button type="reset" @click="resetCat()">Reset</button>
      <cat-card :cat="newCat" />
    </div>
    <cat-card v-for="(item, index) in listOfCats" v-bind:key="index" :cat="item" />
  </div>
</template>

<script>
import CatCard from "./components/CatCard.vue";

export default {
  name: "App",
  data: function () {
    return {
      newCat: {
        title: "",
        msg: "",
        link: "",
        visible: true,
        image: "",
      },
      listOfCats: [
        {
          title: "Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          image: "https://images.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg",
        },
        {
          title: "Big Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          image:
            "https://d3544la1u8djza.cloudfront.net/APHI/Blog/2016/10_October/Do+Cats+Get+Pink+Eye+_+ASPCA+Pet+Health+Insurance+_+orange+tabby+cat+with+green+eyes-min.jpg",
        },
        {
          title: "Bigger Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          image:
            "https://media-cldnry.s-nbcnews.com/image/upload/t_fit-760w,f_auto,q_auto:best/rockcms/2022-08/220805-domestic-cat-mjf-1540-382ba2.jpg",
        },
        {
          title: "Biggest Cats",
          msg: "Welcome to Your Vue.js App",
          link: "http://www.cats.com",
          visible: true,
          image:
            "https://i.pinimg.com/474x/2c/8d/47/2c8d47ae73ff9469c50503c1b3dd3d33--largest-domestic-cat-cat-face.jpg",
        },
      ],
    };
  },
  components: {
    CatCard,
  },
  methods: {
    addCat: function () {
      this.listOfCats.unshift(this.newCat);
      this.resetCat();
    },
    resetCat: function () {
      this.newCat = {
        title: "",
        msg: "",
        link: "",
        visible: true,
        image: "",
      };
    },
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
.newCat {
  width: 300px;
  border: 1px solid #e6e6e6;
  padding: 10px;
  margin: 0 auto;
  margin-bottom: 20px;
}
</style>
