<template>
    <div class="q-pa-md centered-container">
      <q-page>
        <q-card class="weather-card" fixed>
          <q-card-section>
            <div class="title">Cek Suhu dan Cuaca di Kota Anda!</div>
          </q-card-section>
          <q-card-section class="search-section">
            <q-input
              v-model="city"
              placeholder="Tambahkan Lokasi"
              dense
              outlined
              class="search-input"
            />
            <q-btn
              @click="fetchWeather"
              label="Cek Cuaca"
              dense
              flat
              class="search-button"
            />
          </q-card-section>
          <q-card-section v-if="loading">
            <div class="loading-text">Loading data...</div>
          </q-card-section>
          <q-card-section v-if="weather">
            <div class="weather-info">
              <div class="info-item">Location: {{ city }}</div>
              <div class="info-item">Temperature: {{ weather.main.temp }}°C</div>
              <div class="info-item">Condition: {{ weather.weather[0].description }}</div>
            </div>
          </q-card-section>
          <q-card-section v-if="error">
            <div class="error-text">Error: {{ error }}</div>
          </q-card-section>
        </q-card>
      </q-page>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        city: '',
        weather: null,
        loading: false,
        error: null
      };
    },
    methods: {
      async fetchWeather() {
        this.loading = true;
        this.weather = null;
        this.error = null;
        try {
          const apiKey = '94bf6d59f86ae95e8071e78240546056';
          const response = await axios.get(
            `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=${apiKey}`
          );
          this.weather = response.data;
        } catch (err) {
          this.error = 'Unable to fetch weather data. Please try again.';
        } finally {
          this.loading = false;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap');
  
  .centered-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  border-radius: 5px;
}

.weather-card {
  max-width: 400px;
  width: 100%;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(145deg, #f5f7fa, #924aff);
  padding: 20px;
  position: fixed;
  top: 50%; /* Menempatkan card tepat di tengah secara vertikal */
  left: 50%; /* Menempatkan card tepat di tengah secara horizontal */
  transform: translate(-50%, -50%); /* Menggeser card sejauh setengah dari ukuran card sendiri */
}

  
  
  .title {
    font-size: 1.4rem;
    font-weight: 600;
    color: #333;
    text-align: center;
    margin-bottom: 1rem;
  }
  
  .search-section {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
  }
  
  .search-input {
    flex-grow: 1;
    margin-right: 10px;
    max-width: 300px;
  }
  
  .search-button {
    padding: 5px 15px;
    background-color: #924aff;
    color: black !important;
    font-weight: 500;
  }
  
  .loading-text, .error-text {
    font-size: 1rem;
    color: #d32f2f;
    font-weight: 500;
    text-align: center;
    margin-top: 1rem;
  }
  
  .weather-info {
    font-size: 1rem;
    color: #333;
  }
  
  .info-item {
    margin: 0.5rem 0;
  }
  </style>
  