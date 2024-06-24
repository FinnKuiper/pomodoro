<template>
  <button @click="startPause">{{ timerOn ? "pause" : "start" }}</button>
</template>

<script>
export default {
  name: "StartPauseButton",
  props: ["timerOn"],
  setup(props) {
    console.log("timerOn", props.timerOn);
  },
  methods: {
    startPause() {
      this.$emit("start-pause");
    },
  },
};
</script>

<style scoped>
button {
  background-color: #8b8b8b;
  color:  white;
  padding: 1rem;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s;
}
</style>