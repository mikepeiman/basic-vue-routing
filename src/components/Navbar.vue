<template>
  <nav>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About-normal</router-link></li>
      <li><router-link :to="{ name: 'About' }">About-bind</router-link></li>
      <li><router-link to="/blog">Blog</router-link></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {};
  }
};
</script>

<style>
nav {
  width: 90vw;
  display: flex;
  justify-content: center;
}
nav ul {
  display: flex;
  width: 80%;
  list-style-type: none;
  flex-direction: row;
  justify-content: space-between;
  /* align-content: space-around; */
  /* align-items: center; */
}
nav ul li {
  justify-content: space-around;

}
</style>

