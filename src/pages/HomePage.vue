<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-avatar size="70px">
          <img src="@/assets/pp1.jpg" alt="Profile Picture">
        </q-avatar>
        <div class="profile-info">
          <div class="name">Muhammad Revi Suryandi</div>
          <div class="student-id">223510431</div>
        </div>
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/tasks" label="TUGAS PERTEMUAN 1-7" />
      </q-tabs>
    </q-header>

    <q-page-container>
      <div class="fixed-container">
        <WeatherPage />
      </div>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import WeatherPage from '../pages/WeatherPage.vue'

export default {
  components: {
    WeatherPage
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap');

* {
  font-family: 'Poppins', sans-serif;
}

.bg-primary {
  background-color: #924aff !important;
}

.text-white {
  color: #fff !important;
}

.q-toolbar {
  padding: 0.5rem;
}

.q-avatar {
  margin-right: 1rem;
}

.profile-info {
  display: flex;
  flex-direction: column;
}

.name {
  font-size: 1.5rem;
  font-weight: bold;
}

.student-id {
  font-size: 1rem;
  color: #ccc;
}

.q-route-tab {
  font-size: 1.2rem;
  font-weight: bold;
}

.q-page-container {
  padding: 1rem;
}

.fixed-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  position: relative;
}

.weather-page {
  padding: 2rem;
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  background: white;
  width: 100%;
  max-width: 400px;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}

.weather-page .title {
  font-size: 1.4rem;
  font-weight: 600;
  color: #333;
  text-align: center;
  margin-bottom: 1rem;
}

.weather-page .search-section {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
}

.weather-page .search-input {
  flex-grow: 1;
  margin-right: 10px;
  max-width: 300px;
}

.weather-page .search-button {
  padding: 5px 15px;
  background-color: #924aff;
  color: black !important;
  font-weight: 500;
}

.weather-page .loading-text,
.weather-page .error-text {
  font-size: 1rem;
  color: #d32f2f;
  font-weight: 500;
  text-align: center;
  margin-top: 1rem;
}

.weather-page .weather-info {
  font-size: 1rem;
  color: #333;
}

.weather-page .info-item {
  margin: 0.5rem 0;
}
</style>
