<template>
    <img @click="$router.push('/')" src="./assets/Pink Red Colorful Birthday Zoom Virtual Background.png" alt="Pink Red Colorful Birthday Zoom Virtual Background">
  <router-view/>
</template>

<style>
/* Some reset css */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #ffcdea;
}

#app {
  font-family: "Happy Monkey", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #9e0f0f;
}

nav {
  padding: 2rem;
}

nav a {
  font-weight: bold;
  color: #2000ad;
  padding: 0 1rem;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #4283b9;
}

img {
  width: 100%;
  height: auto;
}
</style>
