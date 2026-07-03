<script setup>
  import {ref , computed } from 'vue'
  const soHo = ref(10)
  function themHo() {
    soHo.value++
  }
  const danhSachHo = ref([
    {
      id: 1, ten: 'Nguyễn Tiến Đạt', phong: '101'
    },
    {
      id: 2, ten: 'Trần Thị Lan', phong: '102'
    },
    {
      id: 3, ten: 'Lê Văn Hùng', phong: '103'
    }
  ])
  function botHo(){
    if(soHo.value > 0)
  {
     soHo.value--
  }
   
  }
</script>

<template>
  <h1> Quản lý khu dân cư </h1>
  <p> Tổng số hộ: {{ soHo }}</p>
  <button @click="themHo"> Thêm Hộ Dân</button>
  <br>
  <button @click="botHo"> Bớt Hộ Dân</button>
  <li v-for="ho in danhSachHo" :key="ho.id">
    {{ ho.ten }} - Phòng {{ ho.phong }}
  </li>
</template>

<style scoped></style>
