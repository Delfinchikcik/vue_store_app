<template>
  <div class="v-main-wrapper">
    <vCatalog/>
    <vCart v-if="CART.length"
    :cart_data="CART"/>
  </div>
</template>

<script>
import vCatalog from "./v-catalog.vue";
import vCart from "./v-cart.vue";
import { mapGetters } from "vuex";

export default {
name: 'v-main-wrapper',
components:{    
  vCart,
  vCatalog
},
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
