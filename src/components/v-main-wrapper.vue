<template>
  <div class="v-main-wrapper">
    <h1 class="v-main-wrapper-title">CATALOG WITH LOVE <span class="heart">&#9829;</span></h1>
    <keep-alive>
      <router-view></router-view>
    </keep-alive>

  </div>
</template>

<script>

import { mapGetters } from "vuex";

export default {
name: 'v-main-wrapper',

props:{},
data(){
    return{
        title: ""
    };
},
computed:{
...mapGetters(['CART'])
},
watch:{},
methods:{},
created(){},
mounted(){}

}
</script>

<style scoped>
.v-main-wrapper{
    max-width: 1400px;
    margin: 0 auto;
}
.v-main-wrapper-title{
  text-align: center;
  color: black;
}
.heart{
  color: red;
}
</style>
