<!-- App.vue -->
<template>
  <div class="app">
    <h1>📦 Relasi Antar Komponen di Vue</h1>

    <!-- Parent mengirim props ke Child -->
    <ChildComponent 
      pesan="Halo dari Komponen Induk!" 
      @event-khusus="tanganiEventKhusus"
    >
      <!-- Slot konten dikirim dari parent ke child -->
      <template #header>
        <h2>Ini adalah Konten Slot Header</h2>
      </template>

      <p>Ini adalah konten slot default.</p>

      <template #footer>
        <p>Ini adalah Konten Slot Footer</p>
      </template>
    </ChildComponent>
  </div>
</template>

<script setup>
// ✅ Pastikan file ChildComponent.vue ada di folder yang sama atau sesuai path
import ChildComponent from './ChildComponent.vue'

function tanganiEventKhusus(payload) {
  alert('Menerima event dari anak: ' + payload)
}
</script>

<style>
.app {
  font-family: sans-serif;
  padding: 20px;
}
</style>
