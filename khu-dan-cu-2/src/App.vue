<script setup lang="ts">
import { ref, computed } from 'vue';
import HoDanItem from './components/HoDanItem.vue';

const tenMoi = ref('')

const danhSachHo = ref([
  {
    id: 1,
    tenChuHo: 'Nguyen Van A',
    soNha: '123',
    daDongPhi: false
  },
  {
    id: 2,
    tenChuHo: 'Tran Thi B',
    soNha: '456',
    daDongPhi: false
  },
]);

const tongHo = computed(() => {
  return danhSachHo.value.length
})

const soHoChuaDong = computed(() => {
  return danhSachHo.value.filter(ho => !ho.daDongPhi).length
})

function themHo() {
  if (tenMoi.value.trim() === '') {
    alert('Vui lòng nhập tên hộ dân!')
    return
  }
  danhSachHo.value.push({
    id: Date.now(),
    tenChuHo: tenMoi.value,
    soNha: '101',
    daDongPhi: false
  })
  tenMoi.value = ''
}

function xoaHo(id: number) {
  danhSachHo.value = danhSachHo.value.filter(h => h.id !== id)
}

function doitt(id: number) {
  const ho = danhSachHo.value.find(h => h.id === id)
  if (!ho) return
  ho.daDongPhi = !ho.daDongPhi
}
</script>

<template>
  <p>Tổng số hộ: {{ tongHo }}</p>
  <p v-if="tongHo === 0"> Không có dân cư nào</p>
  <p>Số hộ chưa đóng phí: {{ soHoChuaDong }}</p>

  <input v-model="tenMoi" placeholder="Nhập tên hộ">
  <button @click="themHo">Thêm hộ dân</button>

  <HoDanItem v-for="ho in danhSachHo" :key="ho.id" :ho="ho" @xoa="xoaHo" @doitth="doitt" />
</template>

<style scoped></style>
