<template>
  <div class="v-main-wrapper">
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
</style>
