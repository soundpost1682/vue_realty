<template>
<div class="black-bg" v-if="modal_status==true">
    <div class="white-bg">
      <img :src="onerooms[select].image" style="width: 100%;">
      <h4>{{onerooms[select].title}}</h4>
      <p>{{ onerooms[select].content }}</p>
      <p>{{ onerooms[select].price }}원</p>
      <Discount/>
      <button @click="$emit('closeModal')">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  name : 'Modal',
  props : {
    onerooms:Array,
    select : Number,
    modal_status : Boolean,

  }
}
</script>

<style></style>