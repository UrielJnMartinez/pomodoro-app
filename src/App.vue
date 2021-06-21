<template>
  <!-- dependiendo del componente que se esta ejecutando en el
  router se aplican las propiedades de las clase -->
  <router-view class="aplication__container"/>
</template>

<style lang="scss">
@import './styles/reset';
@import './styles/layaut';
body {
  margin: 0;
  padding: 0;
  // css variables
  // colors

  --application-color-primary: #E23434;
  --application-color-accent: #333745;
  --application-color-text: #FFFFFF;
}

* {
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
