<template>
  
  <div class="black-bg" v-if="modal_status==true">
    <div class="white-bg">
      <img :src="onerooms[select].image" style="width: 100%;">
      <h4>{{onerooms[select].title}}</h4>
      <p>{{ onerooms[select].content }}</p>
      <p>{{ onerooms[select].price }}원</p>
      <button @click="modal_status=false">Close</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="jak in menus" :key="jak">{{ jak }}</a>
  </div>
  
  <div v-for="(oneroom,i) in onerooms" :key="i">
    <img :src="onerooms[i].image" class="room-img">
    <H4 @click="modal_status=true; select=i">{{ onerooms[i].title }}</H4>
    <p >${{ onerooms[i].price }}</p>
    
    
  </div>
  
</template>

<script>
import data from './assets/oneroom.js'

var arr = []
export default {
  name : 'App',
  data(){
    return {
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