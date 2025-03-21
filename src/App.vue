<template>
  <div class="menu">
    <a v-for="jak in menus" :key="jak">{{ jak }}</a>
  </div>
  <div>
    <H4>{{ products[0] }}</H4>
    <p >{{ 500 }}</p>
    <button @click="cnt++">Report Fake</button> <span>No.count : {{ cnt }}</span>
  </div>
  <div>
    <H4>{{ products[1] }}</H4>
    <p >{{ 500 }}</p>
    
  </div>
  <div>
    <H4>{{ products[2] }}</H4>
    <p >{{ 500 }}</p>
  </div>
</template>

<script>
var arr = []
export default {
  name : 'App',
  data(){
    return {
      cnt : 0,
      menus : ['Home','Products','About'],
      products:['Vancouver','Surrey','Langley'],
      
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