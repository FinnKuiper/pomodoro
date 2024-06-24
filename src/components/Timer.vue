<template>
  <div :class="isBreak ? 'break' : ''">
    <h1>Pomodoro timer</h1>
    <p>{{ timerInMinutes }}</p>
    <p>{{ isBreak ? "Break" : "Work" }}</p>
    <start-pause-button @start-pause="startPause" :timerOn="timerOn" />
  </div>
</template>

<script>
import StartPauseButton from "./StartPauseButton.vue";

export default {
  name: "Timer",
  components: {
    StartPauseButton,
  },
  data() {
    return {
      time: 1500,
      timerInMinutes: "25:00",
      break: 5,
      isBreak: false,
      timerOn: false,
    };
  },
  mounted() {
    this.timerInMinutes = this.timeToMinutesAndSeconds();
    setInterval(() => {
      if (!this.timerOn) return;
      this.time--;
      document.title = this.timerInMinutes;
      this.timerInMinutes = this.timeToMinutesAndSeconds();
      if (this.time === 0) {
        if (this.isBreak) {
          alert("Break is over, get back to work!");
        } else {
          alert("Time to take a break!");
        }
        this.isBreak = !this.isBreak;
        this.time = this.isBreak ? this.break * 60 : 25 * 60;
      }
    }, 1000);
  },
  methods: {
    startPause() {
      this.timerOn = !this.timerOn;
    },
    timeToMinutesAndSeconds() {
      const minutes = Math.floor(this.time / 60);
      const seconds = this.time - minutes * 60;
      return `${minutes}:${seconds < 10 ? "0" : ""}${seconds}`;
    },
  },
};
</script>

<style scoped>
p {
  font-size: 2rem;
  text-align: center;
}
div {
  background-color: #000;
  width: 90%;
  height: 40%;
  color: white;
  padding: 2rem;
  border-radius: 0.5rem;
  margin: 0 auto;
  text-align: center;
  margin-top: 8rem;
}
.break {
  background-color: #f0f0f0;
  color: #333;
}
</style>