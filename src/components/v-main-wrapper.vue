<template>
  <div class="v-main-wrapper">

    <vCatalog/>
    <vCart/>
  </div>
</template>

<script>
import vCatalog from "./v-catalog.vue";
import vCart from "./v-cart.vue";

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
computed:{},
watch:{},
methods:{},
created(){},
mounted(){}

}
</script>

<style scoped>
.v-main-wrapper{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    max-width: 1400px;
    margin: 0 auto;
}
</style>
