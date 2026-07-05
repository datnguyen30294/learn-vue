<script setup>
    const props = defineProps({
        ho : Object
    })
    const emit = defineEmits(['xoa', 'doitt'])
</script>
<template>
    <li>
         {{ ho.ten }} - Phòng {{ ho.phong }} - {{ ho.tth }}
        <button @click="emit('xoa', ho.id)">Xoá Hộ</button>
        <button @click="emit('doitt',ho.id)">Đổi trạng thái</button>
    </li>  
</template>
<style scoped></style>