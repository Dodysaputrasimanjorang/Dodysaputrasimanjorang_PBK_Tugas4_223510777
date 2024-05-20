<template>
  <div id="app">
    <div class="container">
      <DayList @day-selected="displayDayDetail"></DayList>
      <DayDetail :day="selectedDay">
        <template v-if="selectedDay">
          <p>Informasi tambahan: {{ additionalInfo }}</p>
        </template>
      </DayDetail>
    </div>
  </div>
</template>

<script>
import DayList from './components/DayList.vue';
import DayDetail from './components/DayDetail.vue';

export default {
  components: { DayList, DayDetail },
  data() {
    return {
      selectedDay: null,
      additionalInfo: 'Anda dapat menambahkan catatan tambahan di sini.'
    };
  },
  methods: {
    displayDayDetail(day) {
      this.selectedDay = day;
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  color: #000000;
}
.container {
  display: flex;
  justify-content: space-around;
  margin: 20px;
}
</style>
