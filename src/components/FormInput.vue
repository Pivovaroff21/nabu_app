<template>
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="input">
        {{item.msg}}
      </label>
      <textarea  v-model="item.inputData" v-if="item.isSmall" id="input" rows="4" class="block p-2.5 w-full text-sm text-gray-700  rounded-lg border leading-tight focus:outline-none focus:shadow-outline " ></textarea>
      <input v-else v-model="item.inputData" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="input" type="text" >
    </div>
</template>






<script >
import { defineComponent } from 'vue';

export default defineComponent({
  name:"FormInput",
  data(){
    return{
      count:0
    }
  },
  props:{
    item:{
      type:Object,
      require:true
    },
  }
})

</script>


<style scoped>

</style>
