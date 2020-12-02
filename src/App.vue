<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
@import "./styles/global-styles.scss";
* {
  margin: 0rem;
  padding: 0rem;
  box-sizing: border-box;
  outline: none;
  transition: all 0.4s ease;
}
#app {
  font-family: $p-font;
  color: #222;
  overflow-x: hidden;
}

p {
  line-height: 1.7rem;
}

button {
  font-family: $p-font;
}

h1,
h2,
h3,
h4 {
  font-family: $title-font;
  color: #2f2f2f;
}
</style>
