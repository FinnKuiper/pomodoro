<template>
  <main>
    <Timer />
  </main>
</template>

<script>
import Timer from "../components/Timer";
export default {
  name: "Home",
  components: {
    Timer,
  },
};
</script>

<style>
main {
  display: flex;
  justify-content: center;
  height: 100vh;
  background-color: #f0f0f0;
}
</style>