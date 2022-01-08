<template>
  <div style="text-align: left; width: 640px">
    <header style="display: flex; justify-content: space-between">
      <form @submit.prevent="fetchData">
        <label for="username">
          <input id="username" v-model="username" type="text" />
        </label>
        <button type="submit">Add</button>
      </form>
      <button type="button">Clear All</button>
    </header>
    <div>
      <GithubUserListItem />
      <GithubUserListItem />
      <GithubUserListItem />
      <GithubUserListItem />
      <GithubUserListItem />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      username: "",
    };
  },

  methods: {
    composeUrl(username: string): string {
      return `https://api.github.com/users/${username}`;
    },
  },

  components: {
    GithubUserListItem: () => import("./github-user-list-item.vue"),
  },

  async fetchData(): Promise<void> {
    this.url = this.composeUrl(this.username);
    const response = await fetch(this.url);
    this.data = await response.json();
  },
});
</script>
