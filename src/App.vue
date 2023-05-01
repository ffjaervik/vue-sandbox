<template>
  <title>Vue Basics</title>
  <h1>Vue Basics</h1>
  <nav>
    <ul>
      <li v-for="link in links" :key="link.name" :href="link.url">{{ link.name }}</li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {
        links: [
          { name: "Home", url: "/" },
          { name: "About", url: "/about" },
          { name: "Contact", url: "/contact" },
          { name: "Login", url: "/login" },
          { name: "Register", url: "/register" },
        ],
      };
    },
  };
</script>

<style></style>
