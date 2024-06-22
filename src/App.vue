<template>
  <q-layout view="hHh lpR fFf" class="app-layout">
    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          <!-- Isi judul aplikasi di sini -->
          Tugas 1-7 Praktikum PBK  
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <!-- Ini adalah tempat di mana konten dari halaman akan dimuat -->
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style scoped>
.app-layout {
  min-height: 100vh;
  background-image: url('@/assets/pp2.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed; /* Ensure background does not move */
}

.bg-primary {
  background-color: #1976d2; /* Ubah sesuai warna yang diinginkan */
}
</style>