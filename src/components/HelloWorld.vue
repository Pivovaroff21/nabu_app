<script >
import { ref } from 'vue'

defineProps({
  msg: String,
})
const count = ref(0)

export default ({
  data(){
    return{
      count:0
    }
  },
  props:{
    msg:{
      type:String,
      require:true
    }
  }
})

</script>

<template>
  <h1>123</h1>
</template>

<style scoped>

</style>
