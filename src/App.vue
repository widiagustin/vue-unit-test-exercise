<template>
  <div id="app">
    <router-view />
    <githubUserList />
    <GithubCard />
  </div>
</template>

<script>
import githubUserList from "../src/components/exercise/github-user-list.vue";
import GithubCard from '../src/components/github-card.vue';

export default {
  components: { 
    githubUserList,
    GithubCard,
     }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
