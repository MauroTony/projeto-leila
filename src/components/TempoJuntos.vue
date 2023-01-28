<template>
  <div class="time-passed">
    <p style="font-size: 50px;">Nós estamos juntos há</p>
    <p>{{ days - 1 }} dias, {{ hours }} horas e {{ seconds }} segundos</p>
    <p style="font-size: 30px;"> Te amo ❤️</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      days: 0,
      hours: 0,
      seconds: 0,
    };
  },
  created() {
    setInterval(() => {
      let currentDate = new Date();
      let targetDate = new Date(2022, 11, 28); // 28 de dezembro de 2022
      let difference = currentDate - targetDate;
      
      let days = Math.floor(difference / (1000 * 60 * 60 * 24));
      let hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      let seconds = Math.floor((difference % (1000 * 60 * 60)) / 1000);

      this.days = days;
      this.hours = hours;
      this.seconds = seconds;
    }, 1000);
  },
};
</script>

<style scoped>
.time-passed {
  font-family: 'Bradley Hand', cursive;
  font-size: 30px;
  color: white
}
</style>