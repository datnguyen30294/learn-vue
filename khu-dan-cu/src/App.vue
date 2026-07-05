<script setup>
  import {ref , computed} from 'vue'
  import HoDanItem from './components/HoDanItem.vue'
  const tenMoi = ref('')
  const soHo = computed(() => {
    return danhSachHo.value.length
  })
  
  function themHo() {
    if(tenMoi.value.trim() === '') {
      alert('Vui lòng nhập tên hộ dân!')
      return
    }
    danhSachHo.value.push({
      id: Date.now(),
      ten: tenMoi.value,
      phong: (danhSachHo.value.length + 1).toString()
    })
    tenMoi.value =''

  }
  function doiTrangThai(id) {
    const ho = danhSachHo.value.find(h => h.id === id)
    if(!ho) return
    if(ho.tth === 'Đã đóng phí') {
      ho.tth = 'Chưa đóng phí'
    } else {
      ho.tth = 'Đã đóng phí'
    }
  }
  const danhSachHo = ref([
    {
      id: 1, ten: 'Nguyễn Tiến Đạt', phong: '101',tth :'Đã đóng phí'
    },
    {
      id: 2, ten: 'Trần Thị Lan', phong: '102',tth :'Chưa đóng phí'
    },
    {
      id: 3, ten: 'Lê Văn Hùng', phong: '103',tth :'Đã đóng phí'
    }
  ])
  function xoaHo(id){
     danhSachHo.value = danhSachHo.value.filter(ho => ho.id !== id)
  }
</script>

<template>
  <h1> Quản lý khu dân cư </h1>
  <p> Tổng số hộ: {{ soHo }}</p>
  
  <button @click="themHo"> Thêm Hộ Dân</button>
  <br>
  <input v-model="tenMoi" placeholder="Nhập tên hộ">
  <HoDanItem v-for ="ho in danhSachHo" :key="ho.id" :ho="ho" @xoa="xoaHo" @doitt="doiTrangThai"/>
  <p v-if="soHo === 0"> Không có dân cư nào</p>
</template>

<style scoped></style>
