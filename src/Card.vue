<template>
<div>
    <img :src="oneroom.image" class="room-img">
    <H4 @click="send">{{ oneroom.title }}</H4>
    <p >${{ oneroom.price }}</p>
  </div>
</template>

<script>
import oneroom from './assets/oneroom';

export default {
  props : {oneroom:Object,}
,
  methods:{
    send(){
      this.$emit('oepnModal', this.oneroom.id)
    }
  }
}
</script>

<style></style>