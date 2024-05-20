<template>
  <div class="day-item" @click="handleClick">
    <h3>Hari {{ day.id }}: {{ day.name }}</h3>
  </div>
</template>

<script>
export default {
  props: ['day'],
  methods: {
    handleClick() {
      this.$emit('day-clicked', this.day);
    }
  }
};
</script>

<style scoped>
.day-item {
  border: 1px solid #ddd;
  padding: 10px;
  margin: 10px 0;
  cursor: pointer;
}
.day-item:hover {
  background-color: #f9f9f9;
}
</style>
