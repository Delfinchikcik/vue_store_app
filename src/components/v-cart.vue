<template>
  <div class="v-cart">
    <div class="v-cart__link_wrapper">
      <router-link :to="{ name: 'catalog' }">
        <div class="v-catalog__link_to_cart">
          <i class="medium material-icons">shop</i>
          {{ CART.length }}
        </div>
        <button class="btn">Назад на главную</button>
      </router-link>
    </div>
    <p class="v-cart_massage" v-if="!CART.length">Вы еще не добавили товары в корзину</p>

    <div class="v-cart__item">
      <vCartItem
        v-for="(item, index) in CART"
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
      />
    </div>
  </div>
</template>

<script>
import vCartItem from './v-cart-item.vue'
import { mapActions, mapGetters } from 'vuex'

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
  computed: {
    ...mapGetters(['CART'])
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
  flex-direction: column;
  border: 2px solid black;
  color: rgb(0, 0, 0);
  align-items: center;
  background-color: beige;
  max-width: 900px;
  background: rgba(81, 116, 43, 0.171);
}
.v-cart__item {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.v-cart__link_wrapper {
  text-align: center;
  color: black;
  font-size: 30px;
}
.v-cart_massage {
  font-size: 40px;
  text-align: center;
}
.v-cart_btn {
  font-size: 25px;
  background-color: rgb(128, 247, 112);
}
.v-cart_btn:hover {
  background-color: #fff;
}
</style>
