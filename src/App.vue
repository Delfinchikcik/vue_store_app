<script>

import vMainWrapper from './components/v-main-wrapper.vue';

export default{
  name: "app",
  components:{
    vMainWrapper,
  }
}

</script>

<template>
  <div id="app">
    <vMainWrapper/>
  </div>
</template>

<style lang="scss">
@import "node_modules/materialize-css/dist/css/materialize.min.css"
</style>
