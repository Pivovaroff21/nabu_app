<template>

    <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <FormInput v-for="item in dataInputList" :item="item"></FormInput>
    </form>



</template>


<script>
import { defineComponent } from 'vue';
import FormInput from "../components/FormInput.vue"
export default defineComponent({
  name:"FormBasicData",
  components:{
    FormInput
  },
  props:{
    dataInputList:{
      type:Array,
      require:true
    }
  },
})


</script>