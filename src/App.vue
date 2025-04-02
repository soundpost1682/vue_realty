<template>
  
  <Modal :onerooms="onerooms" :select="select" :modal_status="modal_status"/>

  <div class="menu">
    <a v-for="jak in menus" :key="jak">{{ jak }}</a>
  </div>

  
  <Card :oneroom="onerooms[i]" v-for="(prod,i) in onerooms" :key="prod"/>
  <Card/>
  <Card/>
  <Card/>
  <Card/>
  <Card/>

  <!-- <div v-for="(oneroom,i) in onerooms" :key="i">
    <img :src="onerooms[i].image" class="room-img">
    <H4 @click="modal_status=true; select=i">{{ onerooms[i].title }}</H4>
    <p >${{ onerooms[i].price }}</p>
  </div> -->
  
</template>

<script>

import data from './assets/oneroom.js'
import Discount from './Discount.vue'
import Modal from './Modal.vue'
import Card from './Card.vue'

var arr = []
export default {
  name : 'App',
  data(){
    return {
      obj : {name:'kim',age:20},
      select : 0,
      onerooms : data,
      modal_status : false,
      cnt : [0,0,0],
      menus : ['Home','Products','About'],
      products:['Vancouver','Surrey','Langley'],
    }
  },
  methods:{
    increase(){
      this.cnt+=1
    }
  },
  components : {
    Discount : Discount,
    Modal : Modal,
    Card:Card,
    
  }
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
.black-bg {
  width: 80%; height: 80%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px; 
}
.white-bg {
  width: 80%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 50%;
  margin-top: 40px;
}
.menu {
  background:darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>