<template>
<div>
    <img :src="oneroom.image" class="room-img">
    <H4>{{ oneroom.title }}</H4>
    <p >${{ oneroom.price }}</p>
  </div>
</template>

<script>
import oneroom from './assets/oneroom';

export default {
  props : {oneroom:Object}
}
</script>

<style></style>