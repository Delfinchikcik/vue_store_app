<template>
  <div class="v-catalog-item">
    <img class="v-catalog-item_img" :src="product_data.image" alt="foto">

    <p class="v-catalog-item_name">{{ product_data.name }}</p>
    <p class="v-catalog-item_price">{{ product_data.price }}</p>
    <button class="v-catalog-item_btn btn" @click="addToCart">Add to cart</button>
  </div>
</template>

<script>
export default {
name: "v-catalog-item",
components:{},

props:{
    product_data:{
        type: Object,
        required: true,
        default(){
            return {}
        }
    }
},

data(){
    return{
        title: "Catalog-item"
    }
},

methods:{
    addToCart(){
        this.$emit('addToCart', this.product_data)
    }
}
}
</script>

<style scoped>
.v-catalog-item{
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;
    border: 2px solid black;
    box-shadow: 0 0 8px 0 gray;
    margin: 10px;
    padding: 10px;
    font-size: 26px;
}
.v-catalog-item_price{
    color: brown;
}
.v-catalog-item_btn{
    background-color: rgb(92, 202, 151);
    border-radius: 10px;
}
.v-catalog-item_img{
max-width: 220px;
max-height: 200px;
}
</style>