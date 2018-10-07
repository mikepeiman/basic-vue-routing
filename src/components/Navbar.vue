<template>
  <nav>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About-normal</router-link></li>
      <li><router-link :to="{ name: 'About' }">About-bind</router-link></li>
      <li><router-link to="/blog">Blog</router-link></li>
      
      <ul>
        <h2>User Profiles</h2>
        <li v-for="(id, index) in userIds" :key="index">
          <router-link :to="{ name: 'ViewProfile', params: { user_id: id } }">{{ id }}</router-link>
        </li>
      </ul>
            <ul>
        <h2>Nav Controls</h2>
        <li><button @click="goHome">Redirect to Home</button></li>
        <li><button @click="goBack">Back</button></li>
        <li><button @click="goForward">Forward</button></li>
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
  },
  methods: {
    goHome() {
      this.$router.push({ name: 'Home' })
    },
    goBack() {
      this.$router.go(-1)
    },
    goForward() {
      this.$router.go(1)
    }
  }
};
</script>

<style>
$color-main: #aa22ff;
nav {
  width: 90vw;
  display: flex;
  justify-content: center;
  
}
nav ul {
  /* display: flex; */
  /* width: 80%;   */
  list-style-type: none;
  flex-direction: row;
  justify-content: space-between;
  /* align-content: space-around; */
  /* align-items: center; */
}
nav ul li {
  justify-content: space-around;
  display: inline-block;
  margin: 0 5px;
}
nav ul ul {
  /* display: flex; */
  flex-direction: column;
}
a {
  color: #a45bac;
  text-decoration: none;
}
a:hover {
  color: #145bff;
}
a.router-link-exact-active {
  /* text-decoration: underline; */
  background: #333;
  color: #eee;
  padding: 5px;
}
/* a:visited {
  color: #145b7c;
} */
</style>

