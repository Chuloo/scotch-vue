<template>
  <div class="about">
    <Hero title="Welcome to Our Team" subtitle="A Small Ragtag Bunch" color="is-warning" />
    <div class="container is-fluid columns is-multiline">
      <div class="column is-2" v-for="user in users" :key="user.login">
        <User v-bind:user="user" />
      </div>
    </div>
  </div>
</template>

<script>
import User from "@/components/User";
import Hero from "@/components/Hero";
export default {
  components: {
    User,
    Hero
  },
  // data for this component goes here
  data() {
    return {
      users: null
    };
  },
  mounted() {
    // grabs data from github
    fetch("https://api.github.com/users?per_page=12")
      .then(res => res.json()) // unwrap the fetch response
      /* eslint-disable no-console */
      .then(data => {
        this.users = data;
        console.log(data);
      });
  }
};
</script>

