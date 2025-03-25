<template>
  <div class="menu">
    <a v-for="jak in menus" :key="jak">{{ jak }}</a>
  </div>
  
  <div>
    <img src="./assets/room0.jpg" alt="">
    <H4>{{ products[0] }}</H4>
    <p >{{ 500 }}</p>
    <button @click="cnt[0]++">Report Fake</button> <span>No.count : {{ cnt[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" alt="">
    <H4>{{ products[1] }}</H4>
    <p >{{ 500 }}</p>
    <button @click="cnt[1]++">Report Fake</button> <span>No.count : {{ cnt[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" alt="">
    <H4>{{ products[2] }}</H4>
    <p >{{ 500 }}</p>
    <button @click="cnt[2]++">Report Fake</button> <span>No.count : {{ cnt[2] }}</span>
  </div>
</template>

<script>
var arr = []
export default {
  name : 'App',
  data(){
    return {
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