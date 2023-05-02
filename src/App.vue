<template>
  <title>{{ pageTitle }}</title>
  <h1>{{ pageTitle }}</h1>
  <nav>
    <ul id="navbar">
      <li v-for="(page, index) in pages" :key="index">
        <a
          aria-current="page"
          :href="page.link.url"
          :title="`This page goes to ${page.link.pageTitle}`"
          @click.prevent="activePage = index"
          >{{ page.link.text }}</a
        >
      </li>
    </ul>
  </nav>
  <h1>{{ pages[activePage].pageTitle }}</h1>
  <p>
    {{ pages[activePage].content }}
  </p>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {
        activePage: 0,
        pages: [
          {
            link: { text: "Home", url: "index.html" },
            pageTitle: "Home Page",
            content: "This is the home page",
          },
          {
            link: { text: "About", url: "about.html" },
            pageTitle: "About Page",
            content: "This is the about page",
          },
          {
            link: { text: "Contact", url: "contact.html" },
            pageTitle: "Contact Page",
            content: "This is the contact page",
          },
        ],
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

  #navbar li,
  a {
    list-style-type: none;
    font-size: 1rem;
    color: #000;
    font-weight: bold;
    text-decoration: none;
    text-transform: uppercase;
    cursor: pointer;
  }
</style>
