<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Rubik';
  overflow-x: hidden;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}

@font-face {
  font-family: 'Rubik';
  font-style: normal;
  font-weight: 200;
  src: url('@/assets/fonts/Rubik-Light.woff') format('woff');
}

@font-face {
  font-family: 'Rubik';
  font-style: normal;
  font-weight: 400;
  src: url('@/assets/fonts/Rubik-Medium.woff') format('woff');
}

@font-face {
  font-family: 'Rubik';
  font-style: normal;
  font-weight: 700;
  src: url('@/assets/fonts/Rubik-Bold.woff') format('woff');
}

@font-face {
  font-family: 'Rubik';
  font-style: normal;
  font-weight: 800;
  src: url('@/assets/fonts/Rubik-Black.woff') format('woff');
}
</style>
