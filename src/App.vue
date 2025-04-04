<template>
  
  <transition name="fade">
  <Modal @closeModal="modal_status=false" :onerooms="onerooms" :select="select" :modal_status="modal_status"/>
  </transition>

  <div class="menu">
    <a v-for="jak in menus" :key="jak">{{ jak }}</a>
  </div>
  <Discount/>

  <button @click="priceSort">Sort by price</button>
  <button @click="sortBack">Reset the sort</button>
  
  <Card @openModal="modal_status=true; select=$event" :oneroom="onerooms[i]" v-for="(prod,i) in onerooms" :key="prod"/>
  

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

export default {
  name : 'App',
  data(){
    return {
      oneroomsOriginal :[...data],
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
    },
    sortBack(){
      this.onerooms = [...this.oneroomsOriginal];
    },
    priceSort(){
      this.onerooms.sort(function(a,b){
        return a.price - b.price
      })
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
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: all 1s;
}
.fade-leave-to {
  opacity: 0;
}


.fade-enter-from {
  transform: translateY(-1000);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0);
}


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