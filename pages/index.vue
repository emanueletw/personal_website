<template>
  <section id="elementName" class="container font-color">
    <div>
      <awesome-logo class="logo-proportions" />
      <h1 class="title">
        emanuele-website1
      </h1>
      <h2 class="subtitle">
        Personal website
      </h2>
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Tempora eligendi ratione doloribus quos, quod nostrum dolorem similique minus voluptate alias enim soluta vitae doloremque consectetur suscipit nobis earum velit dolor?</p>
      <div class="links">
        <nuxt-link to="/about" class="button--grey">About</nuxt-link>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import AwesomeLogo from '~/components/AppLogo'

export default {
  components: {
    AwesomeLogo
  }
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  padding: 5% 5% 5% 5%;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  text-align: center;
}
.font-color {
  color: rgb(76, 24, 83);
}
.logo-proportions {
  margin: 5%;
  background-color: red;
  border: 10px solid gold;
  box-sizing: content-box;
  transition: box-shadow 1s ease-in-out;
}

.logo-proportions:hover{
  box-shadow: 0 0 10px 10px rgba(0, 0, 0, 0.3);
}

/* this is a note to remember the code. */

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
