<template>
  <nav>
    <h1>Pomodoro</h1>
    <menu>
      <li>
        <router-link to="/">Home</router-link>
      </li>
      <li>
        <router-link to="/about">About</router-link>
      </li>
    </menu>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped lang="sass">
nav
  display: flex
  justify-content: space-between
  padding-block: 1rem
  padding-inline: 16rem
  menu
    display: flex
    gap: 2rem
    justify-content: center
    align-items: center
    li
      margin-left: 1rem
      list-style: none
      a
        text-decoration: none
        color: #333
        transition: color 0.3s
        &:hover
          color: #666
</style>