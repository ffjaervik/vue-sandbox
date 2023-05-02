<template>
  <nav
    class="navbar navbar-expand-lg"
    :class="navbarClasses"
  >
    <div class="container-fluid">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0 black">
        <li v-for="(page, index) in pages" :key="index" class="nav-item">
          <a
            class="nav-link"
            :class="{ active: activePage === index }"
            aria-current="page"
            :href="page.link.url"
            :title="`This page goes to ${page.link.pageTitle}`"
            @click.prevent="activePage = index"
            >{{ page.link.text }}</a
          >
        </li>
      </ul>
      <form class="d-flex">
        <button class="btn btn-primary" @click.prevent="setDarkNavbar = !setDarkNavbar">Change Navbar</button>
      </form>
    </div>
  </nav>
  <h1>{{ pages[activePage].pageTitle }}</h1>
  <p>
    {{ pages[activePage].content }}
  </p>
</template>

<script>
  export default {
    name: "App",
    computed:{
      navbarClasses(){
        return {
          'navbar-light': !this.setDarkNavbar,
          'bg-light': !this.setDarkNavbar,
          'navbar-dark': this.setDarkNavbar,
          'bg-dark': this.setDarkNavbar,
        }
      }
    },
    data() {
      return {
        activePage: 0,
        setDarkNavbar: false,
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
  /* #navbar {
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
  } */
</style>
