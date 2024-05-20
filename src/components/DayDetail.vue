<template>
    <div v-if="day" class="day-detail">
      <h2>Detail Hari</h2>
      <h3>Hari {{ day.id }}</h3>
      <input v-model="day.name" placeholder="Nama Hari">
      <textarea v-model="day.activities" placeholder="Kegiatan"></textarea>
      <slot></slot>
    </div>
  </template>
  
  <script>
  export default {
    props: ['day']
  };
  </script>
  
  <style scoped>
  .day-detail {
    max-width: 600px;
    margin: 20px auto;
    text-align: center;
  }
  input, textarea {
    width: 100%;
    margin: 10px 0;
    padding: 8px;
    box-sizing: border-box;
  }
  </style>
  