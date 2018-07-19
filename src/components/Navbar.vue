<template>
  <nav>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About-normal</router-link></li>
      <li><router-link :to="{ name: 'About' }">About-bind</router-link></li>
      <li><router-link to="/blog">Blog</router-link></li>
      <ul>
        <li><h2>User Profiles</h2></li>
        <li v-for="(id, index) in userIds" :key="index">
          <router-link :to="{ name: 'ViewProfile', params: { user_id: id } }">{{ id }}</router-link>
        </li>
      </ul>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ['1','2','3','4']
    };
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
  /* width: 80%;   */
  list-style-type: none;
  flex-direction: row;
  justify-content: space-between;
  /* align-content: space-around; */
  /* align-items: center; */
}
nav ul li {
  justify-content: space-around;
  margin: 0 5px;
}
nav ul ul {
  display: flex;
  flex-direction: column;
}
</style>

