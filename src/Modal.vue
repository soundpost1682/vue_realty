<template>
<div class="black-bg" v-if="modal_status==true">
    <div class="white-bg">
      <img :src="onerooms[select].image" style="width: 100%;">
      <h4>{{onerooms[select].title}}</h4>
      <p>{{ onerooms[select].content }}</p>
      <p> {{ month }} month selected : {{ onerooms[select].price*select }}원</p>
      <Discount/>
      <input v-model="month">
      <button @click="$emit('closeModal')">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  name : 'Modal',
  data(){
    return {
    month:1,
  }},
  watch :{
    month(a){
      if (a>13){
        alert('No more than 13')
      }

    }
  },
  props : {
    onerooms:Array,
    select : Number,
    modal_status : Boolean,

  }
}
</script>

<style></style>