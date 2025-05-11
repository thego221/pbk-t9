<template>
  <div class="child">
    <!-- Slot bernama -->
    <header><slot name="header" /></header>

    <!-- Props -->
    <p>{{ pesan }}</p>

    <!-- Emit event ke parent -->
    <button @click="kirimEvent">Klik untuk Mengirim Event ke Induk</button>

    <!-- Default slot -->
    <div class="default-slot">
      <slot />
    </div>

    <!-- Slot bernama -->
    <footer><slot name="footer" /></footer>
  </div>
</template>

<script setup>
const props = defineProps(['pesan'])
const emit = defineEmits(['event-khusus'])

function kirimEvent() {
  emit('event-khusus', 'Halo dari Komponen Anak!')
}
</script>

<style>
.child {
  border: 1px solid #ccc;
  padding: 16px;
  border-radius: 8px;
}
</style>
