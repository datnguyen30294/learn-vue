<script setup lang="ts">
    interface HoDan {
        id: number
        tenChuHo: string
        soNha: string
        daDongPhi: boolean
    }
    const props = defineProps<{
        ho: HoDan
    }>();
   const emit = defineEmits(['xoa','doitth'])
</script>
<template>
        <span>{{ ho.tenChuHo }} - {{ ho.soNha }} </span>
        <span v-if = "ho.daDongPhi"> hộ đã đóng phí</span>
        <span v-else>hộ chưa đóng phí</span>
       <button @click="emit('xoa', ho.id)">Xoá hộ</button>
       <button @click="emit('doitth', ho.id)">Đổi trạng thái</button>
</template> 
<style>
</style>