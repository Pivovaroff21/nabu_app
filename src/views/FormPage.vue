<template>
   <div class="w-full max-w-screen-md ml-auto mr-auto mt-2">
    <FormBasicData :dataInputList="dataInputList"></FormBasicData>
    <FormOptionalData :dataInputListOptional="dataInputListOptional"></FormOptionalData>
    <button @click="sendEmail" class="shadow bg-purple-500 hover:bg-purple-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
      Відправити
    </button>
  </div>


</template>


<script>
// import {FormBasicData,FormOptionalData} from "../components"
import FormBasicData from "../components/FormBasicData.vue"
import FormOptionalData from "../components/FormOptionalData.vue"
import emailjs from "emailjs-com";
export default {
  name:"FormPage",
  components:{
    FormBasicData,
    FormOptionalData,
  },
  data(){
    return{
      dataInputList:[
        {msg:"ПІБ особи яка ймовірно вчинила правопорушення",inputData:"",variable:"profName"},
        {msg:"Посада",inputData:"",variable:"posada"},
        {msg:"Місце роботи",inputData:"",variable:"place"},
        {msg:"Опис ситуації",inputData:"", isSmall:true,variable:"description"}
      ],
      dataInputListOptional:[
        {msg:"Ваше ПІБ",inputData:"",variable:"fromName"},
        {msg:"Номер телефону",inputData:"",variable:"fromPhone"},
      ],
      formData:{}
    }
  },
  methods: {
    sendEmail(e) {
        this.dataInputList.forEach((item)=>{
        this.formData[item.variable] = item.inputData
      })
        this.dataInputListOptional.forEach((item)=>{
        if(!item.inputData){
          this.formData[item.variable] = "Анонімно"
        }else{
          this.formData[item.variable] = item.inputData
        }

      })
      try {
        emailjs.send('service_439weax', 'template_o9f0w8m',
        {

          ... this.formData
        },
         'gDPJns2l5uUlHFowZ');

      } catch(error) {
          console.log({error})
      }

    },
  }
}


</script>