<template>
    <div class="day-list">
      <h2>Daftar Hari</h2>
      <div v-for="day in days" :key="day.id">
        <DayItem :day="day" @day-clicked="showDayDetail"></DayItem>
      </div>
      <button @click="addNewDay">Tambah Hari Baru</button>
    </div>
  </template>
  
  <script>
  import DayItem from './DayItem.vue';
  
  export default {
    components: { DayItem },
    data() {
      return {
        days: [
          { id: 1, name: 'Senin', activities: '' },
          { id: 2, name: 'Selasa', activities: '' },
        ]
      };
    },
    methods: {
      showDayDetail(day) {
        this.$emit('day-selected', day);
      },
      addNewDay() {
        const newId = this.days.length + 1;
        this.days.push({ id: newId, name: '', activities: '' });
      }
    }
  };
  </script>
  
  <style scoped>
  .day-list {
    max-width: 600px;
    margin: 0 auto;
    text-align: center;
  }
  button {
    margin-top: 10px;
  }
  </style>
  