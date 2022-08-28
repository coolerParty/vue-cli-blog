<template>
  <div class="newCat">
    <h3>Add a Cat</h3>
    <div><span>Title: </span> <input type="text" v-model="newCat.title" /></div>
    <div><span>Message: </span> <input type="text" v-model="newCat.msg" /></div>
    <div><span>Link: </span> <input type="text" v-model="newCat.link" /></div>
    <div><span>Image URL: </span> <input type="text" v-model="newCat.image" /></div>
    <div>
      <span>Wholesale Price:</span>
      <input type="number" step="0.01" v-model="wholesalePrice" />
    </div>
    <br />
    <button type="submit" @click="addNewCat()">Add Cat</button>
    <button type="reset" @click="resetCat()">Reset</button>
    <cat-card :cat="newCat" />
  </div>
</template>

<script>
import CatCard from "./CatCard.vue";
export default {
  name: "CatForm",
  components: {
    CatCard,
  },
  data: function () {
    return {
      newCat: {
        title: "",
        msg: "",
        link: "",
        visible: true,
        image: "",
        price: 0.0,
        wholesale: 0,
      },
    };
  },
  computed: {
    wholesalePrice: {
      get: function () {
        return this.newCat.wholesale;
      },
      set: function (value) {
        let amount = parseFloat(value);
        let markup = parseFloat(amount * 0.2);
        this.newCat.wholesale = amount;
        this.newCat.price = amount + markup;
      },
    },
  },
  methods: {
    addNewCat: function () {
      this.$emit("create-new-cat", this.newCat);
      this.resetCat();
    },
    resetCat: function () {
      this.newCat = {
        title: "",
        msg: "",
        link: "",
        visible: true,
        image: "",
        price: 0.0,
        wholesale: 0,
      };
    },
  },
};
</script>

<style scoped>
.newCat {
  width: 300px;
  border: 1px solid #e6e6e6;
  padding: 10px;
  margin: 0 auto;
  margin-bottom: 20px;
}
</style>
