<template>
  <div class="q-pa-md">
    <q-page>
      <q-list bordered padding>
        <a href="#" v-for="taskNumber in taskNumbers" :key="taskNumber" class="q-item" @click="goToTask(taskNumber)">
          {{ `Ini tugas ${taskNumber}, Mau liat? Klik aja ce'es` }}
        </a>
      </q-list>
    </q-page>
  </div>
</template>

<script>
export default {
  data() {
    return {
      taskNumbers: [1, 2, 3, 4, 5, 6, 7]
    };
  },
  methods: {
    goToTask(taskNumber) {
      const taskLinks = {
        1: "https://tugas-pbk-223510431.vercel.app/",
        2: "https://tugas2-prakpbk-muhammadrevisuryandi-223510431.vercel.app/",
        3: "https://tugas3-pbk-muhammadrevisuryandi-223510431-4b.vercel.app/",
        4: "https://tugas4-muhammadrevisuryandi-223510431.vercel.app",
        5: "https://reppshop.vercel.app/",
        6: "https://t6revi.vercel.app/",
        7: "https://t7revii.vercel.app/"
      };
      window.open(taskLinks[taskNumber], '_blank');
    }
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap');

.q-pa-md {
  padding: 16px;
  background-image: url('/assets/pp2.jpg');
  background-size: cover;
  background-position: center;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: flex-start; /* Menengahkan konten di tengah dan sedikit lebih ke bawah */
  position: fixed;
  top: 50px; /* Menyisipkan jarak dari atas */
  left: 0;
  right: 0;
  bottom: 0;
}

.q-list {
  max-width: 400px;
  margin: 0 auto;
  background: #dbc6fa;
  border-radius: 10px;
  padding: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.q-item {
  display: block;
  padding: 12px 16px;
  border-radius: 5px;
  background-color: #c8abf5;
  margin-bottom: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
  font-family: 'Poppins', sans-serif;
  font-weight: 500;
  text-decoration: none;
  color: inherit;
}

.q-item:hover {
  background-color: #b89ee7;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}
</style>
