<template>
  <div class="v-catalog">
    <vCatalogItem
      v-for="product in PRODUCTS"
      :key="product.article"
      :product_data="product"
      @addToCart="addToCart"
    />
  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item.vue'
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'v-catalog',

  components: {
    vCatalogItem
  },

  props: {},

  data() {
    return {}
  },

  computed: {
    ...mapGetters(['PRODUCTS'])
  },

  methods: {
    ...mapActions(['GET_PRODUCTS_FROM_API', 'ADD_TO_CART']),
    addToCart(data) {
      this.ADD_TO_CART(data)
    }
  },

  mounted() {
    this.GET_PRODUCTS_FROM_API()
      .then(() => {
        if (this.PRODUCTS) {
          console.log(this.PRODUCTS)
        }
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>

<style scoped>
.v-catalog {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
  width: 1000px;
}
</style>
