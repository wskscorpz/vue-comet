<template>
  <div class="hello">
    <div v-if="hasComet">
      <img src="../assets/comet.png"/>
      Comet installed!
    </div>
    <div v-else>
      Comet not installed!
    </div>
  </div>
</template>

<script>

import { thorify } from 'thorify'
import { extend } from 'thorify/dist/extend'
const Web3 = require("web3"); // Recommend using require() instead of import here

export default {
  name: 'hello',
  computed: {
    // a computed getter
    hasComet: function () {
      if (typeof thor !== 'undefined') {
        // Use thor provider
        let web3js = new Web3(thor);
        
        // Extend web3 to connect to VeChain Blockchain
        extend(web3js)

        //thor.enable()
        return true
      } 
      return false
    }
  },
  data () {
    return {
      //msg: 'Comet needed'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
