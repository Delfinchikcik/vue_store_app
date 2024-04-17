<template>
  <div class="v-cart-item">
    <img class="v-cart-item_img" :src="cart_item_data.image" alt="foto" />
    <div class="v-cart-item-text">
      <p>{{ cart_item_data.name }}</p>
      <p>{{ cart_item_data.price }}</p>
      <p>{{ cart_item_data.article }}</p>
      <p>{{ cart_item_data.about }}</p>
    </div>
    <div class="v-cart-item__quantity">
      <p>Quantity</p>
      <span>{{ cart_item_data.quantity }}</span>
    </div>
    <button class="v-cart-item-btn bnt" @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'v-cart-item',

  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart', this.cart_item_data)
    }
  }
}
</script>

<style scoped>
.v-cart-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 grey;
  padding: 20px;
  margin: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 2px solid black;
  text-align: center;
  background-color: azure;
  height: 420px;
  min-width: 300px;
}
.v-cart-item_img {
  height: 200px;
  width: 70%;
}
.v-cart-item-text {
  text-align: center;
}
.v-cart-item-btn {
  background-color: rgb(205, 247, 53);
}
.v-cart-item-btn:hover {
  background-color: rgb(240, 103, 103);
}
</style>
