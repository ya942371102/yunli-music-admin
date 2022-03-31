<script setup>
import { ref } from 'vue'
import { sayHello } from '../api/hello'

const count = ref(0)
const message = ref("毅力音乐和后台")

const hi = () =>{
  sayHello().then(res=>{
    message.value = res.data
  })
  //message.value = '已请求'
}

</script>

<template>
  <h1>{{ message }}</h1>
    <q-btn color="primary" @click="count++"> 点击次数 ：{{ count }}</q-btn>
      <br/>
      <br/>
    <q-btn color="primary" @click="hi"> 请求接口</q-btn>

</template>

<style scoped>
a {
  color: #42b983;
}

.button-container{
  width: 50%;
  display: flex;
  flex-direction: row;
}
</style>
