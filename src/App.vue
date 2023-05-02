<template>
  <title>{{ pageTitle }}</title>
  <h1>{{ pageTitle }}</h1>
  <nav>
    <ul id="navbar">
      <li v-for="(link, index) in links" :key="index">
        <a :href="link.url" :title="`This page goes to ${link.name}`">{{ link.name }}</a>
      </li>
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
        pageTitle: "Vue Basics",
      };
    },
  };
</script>

<style>
  #navbar {
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: flex-start;
    gap: 50px;
  }

  #navbar li, a {
    list-style-type: none;
    font-size: 1rem;
    color: #000;
    font-weight: bold;
    text-decoration: none;
    text-transform: uppercase;
    cursor: pointer;
  }
</style>
