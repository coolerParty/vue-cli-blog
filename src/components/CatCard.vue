<template>
  <a :href="cat.link" v-if="cat.title">
    <div :class="[cat.visible ? 'visible' : 'invisible', 'catCard']">
      <div v-if="cat.visible == true">
      <img v-if="cat.image" :src="cat.image" alt="" class="catImage">
        <h1>
          {{ cat.title }}
        </h1>
        <p>{{ cat.msg }}</p>
        <div>Price: $ {{ cat.price.toFixed(2) }}</div>
        <div>Tax: $ {{ tax.toFixed(2) }}</div>
        <div>Total: $ {{ total.toFixed(2) }}</div>
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
  computed: {
    tax: function() {
      return this.cat.price * .03;
    },
    total: function() {
      return this.cat.price + this.tax;
    }
  }
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
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>
