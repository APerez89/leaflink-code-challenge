<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
:root {
  --healine-font: 'Poppins', sans-serif;
  --headline-size-bg: 56px;
  --headline-size-md: 48px;
  --headline-size-sm: 32px;
  --body-font: 'Noto Sans', sans-serif;
  --body-size-bg: 18px;
  --body-size-sm: 16px;
  --blue-dream: #0072f0;
  --green-crack: #1ce0ad;
  --la-confidential: #0022ac;
  --nyc-diesel: #01bbb4;
  --white-widow: #ffffff;
  --grandaddy-purp: #1b1443;
}

* {
  box-sizing: border-box;
  margin: 0;
}

html,
body {
  width: 100%;
  display: flex;
  justify-content: center;
}

#app {
  max-width: 1024px;
  height: 100vh;
  padding: 40px;
  background-color: #afafaf;
  font-family: var(--healine-font);
  color: var(--grandaddy-purp);
  display: flex;
  justify-content: center;
}
h1 {
  font-size: var(--headline-size-bg);
}
h2 {
  font-size: var(--headline-size-md);
}
p {
  font-family: var(--body-font);
  font-size: var(--body-size-bg);
}
</style>
