# BÀI HỌC 3: VUE.JS CƠ BẢN

> File này là **lộ trình + bài tập**, không phải code chạy được ngay.
> Vue thường cần một dự án (Vite). Khi sẵn sàng dựng project thật,
> mình sẽ hướng dẫn từng bước `npm create vue@latest`.

## Ý tưởng cốt lõi cần hiểu trước
Trước khi gõ code, hãy tự trả lời (viết ra giấy hoặc dưới mỗi câu):

1. **Reactivity là gì?** Vì sao khi dữ liệu đổi thì giao diện tự cập nhật?
   - Trả lời của bạn:

2. **Component là gì?** Tại sao chia UI thành nhiều component lại tốt hơn 1 file khổng lồ?
   - Trả lời của bạn:

## Cấu trúc 1 component (Single File Component - `.vue`)
Một file `.vue` có 3 phần. Bạn thử đoán mỗi phần dùng để làm gì:

```vue
<script setup>
// Phần logic: khai báo dữ liệu, hàm...
</script>

<template>
  <!-- Phần giao diện HTML -->
</template>

<style scoped>
/* Phần CSS */
</style>
```

- `<script setup>` dùng để: _(bạn điền)_
- `<template>` dùng để: _(bạn điền)_
- `scoped` trong `<style>` nghĩa là gì? _(bạn điền)_

## Bài tập tư duy (chưa cần code)
Áp vào dự án **quản lý khu dân cư** của bạn:

- [ ] Liệt kê 3 component bạn nghĩ trang "Danh sách hộ dân" sẽ cần.
- [ ] Dữ liệu nào nên là `ref`/`reactive` (thay đổi được)?
- [ ] Khi bấm nút "Thêm hộ dân", luồng dữ liệu đi như thế nào?

## Khái niệm sẽ học dần (checklist)
- [ ] `ref()` và `reactive()`
- [ ] Directive: `v-if`, `v-for`, `v-model`, `v-bind`, `v-on`
- [ ] Props (truyền dữ liệu cha → con)
- [ ] Emit (con báo sự kiện lên cha)
- [ ] `computed` và `watch`

---
Khi bạn điền xong phần suy nghĩ ở trên, nhắn mình để cùng dựng project Vue thật nhé.
