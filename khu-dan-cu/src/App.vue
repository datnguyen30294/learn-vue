<script setup>
  import {ref} from 'vue'
  const soHo = ref(10)
  function themHo() {
    soHo.value++

  }
  function botHo(){
    if(soHo.value > 0)
    soHo.value--
  }
</script>

<template>
  <h1> Quản lý khu dân cư </h1>
  <p> Tổng số hộ: {{ soHo }}</p>
  <button @click="themHo"> Thêm Hộ Dân</button>
  <br>
  <button @click="botHo"> Bớt Hộ Dân</button>
</template>

<style scoped></style>
