<template>
  <div id="app" class="c-app" tid="c-app">
    <header class="c-app__header" tid="c-app__header">
      <router-link to="/logout" v-if="isAuthenticated" tid="c-app__logout-link">Logout</router-link>
    </header>
    <main class="c-app__main" tid="c-app__main">
      <router-view></router-view>
    </main>
    <footer class="c-app__footer" tid="c-app__footer">
      <router-link to="/about" tid="c-app__about-link">About</router-link>
    </footer>
  </div>
</template>

<script>
import Vue from 'vue';
import { Component } from 'vue-property-decorator';

import { AuthGetter } from './store';

@Component
export default class App extends Vue {
  @AuthGetter isAuthenticated;
}
</script>

<style>
*,
*:before,
*:after {
  box-sizing: border-box;
}

html {
  font-size: 10px;
  font-family: Segoe UI, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
  background-color: #fff;
}

body {
  margin: 0;
  padding: 0;
  height: 100vh;
  min-width: 320px;
  font-size: 1.6rem;
  background: radial-gradient(
    ellipse at center,
    rgba(4, 34, 62, 0.7) 0%,
    rgb(4, 34, 62) 100%
  );
}

input {
  border: 1px solid #ccc;
  border-radius: 2px;
  padding: 0.9rem;
  line-height: 2rem;
  color: inherit;
  font-size: 1.4rem;
  width: 100%;
}

:focus,
input:focus {
  outline: rgb(2, 116, 169, 0.5) auto 0.5rem;
}

label {
  display: block;
  line-height: 2rem;
  font-weight: bolder;
}

label + input {
  margin-top: 0.5rem;
}

p {
  margin: 0;
}

a {
  color: #333;
}

a:link,
a:visited,
a:hover,
a:active {
  color: rgb(2, 116, 169);
  text-decoration: underline;
}

a:hover,
a:active {
  color: rgba(2, 116, 169, 0.75);
}

a:focus {
  outline-style: dashed;
  outline-width: 0.1rem;
}

pre {
  white-space: pre-wrap;
  word-break: break-word;
}

.c-app {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.c-app__header {
  border-bottom: 1px solid rgba(17, 4, 62, 1);
  background-color: rgba(17, 4, 62, 0.25);
  padding: 2rem 4rem;
  text-align: right;
  min-height: 6rem;
  line-height: 2rem;
}

.c-app__main {
  flex-grow: 1;
  flex-basis: 100%;
  padding: 2rem;
}

.c-app__footer {
  padding: 2rem 4rem;
  border-top: 1px solid rgba(17, 4, 62, 1);
  background-color: rgba(17, 4, 62, 0.25);
}
</style>
