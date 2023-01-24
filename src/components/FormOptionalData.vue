<template>

  <div class="flex items-center max-w-screen-md ml-auto mr-auto mb-4">
    <input id="link-checkbox" type="checkbox" @change="isAnon = !isAnon" class="w-4 h-4 text-purple-600 ">
    <label for="link-checkbox" class="ml-2 text-sm font-medium text-gray-900 ">Написати відгук <span class="text-purple-600 dark:text-purple-600 hover:underline">анонімно</span>.</label>
  </div>
    <form v-if="!isAnon" class=" bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <FormInput v-for="item in dataInputListOptional" :item="item"></FormInput>
    </form>


</template>


<script>
import { defineComponent } from 'vue';
import FormInput from "../components/FormInput.vue"
export default defineComponent({
  name:"FormOptionalData",
  components:{
    FormInput
  },
  props:{
    dataInputListOptional:{
      type:Array,
      require:true
    },
  },
  data(){
  return{
    isAnon:false
  }}
})


</script>