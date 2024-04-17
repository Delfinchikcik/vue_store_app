<template>
  <div class="v-cart">
    <div class="v-cart__item">
      <vCartItem
        v-for="(item, index) in cart_data"
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
      />
    </div>
  </div>
</template>

<script>
import vCartItem from './v-cart-item.vue'
import { mapActions } from 'vuex'

export default {
  name: 'v-cart',
  components: {
    vCartItem
  },
  props: {
    cart_data: {
      type: Array,
      default() {
        return []
      }
    }
  },
  data() {
    return {
      title: 'Cart'
    }
  },
  methods: {
    ...mapActions(['DELETE_FROM_CART']),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index)
    }
  }
}
</script>

<style scoped>
.v-cart {
  display: flex;
  border: 2px solid black;
  color: rgb(0, 0, 0);
  align-items: center;
background-color: beige;
max-width: 900px;
}
.v-cart__item {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;

}
</style>
