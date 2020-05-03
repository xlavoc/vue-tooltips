<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">

@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

body {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  line-height: 1.6rem;
}

#app {
  width: 98vw;
  max-width: 1600px;
  margin: auto;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
hr {
  border-top: 1px dotted #eee;
  border-bottom: none;
  border-left: none;
}
button {
  //display: block;
  float: right;
  clear:right;
  //margin-top: .2rem;
  background: #fff;
  padding: .3rem;
  border: 1px solid #ccc;
  border-radius: 2px;
  font-family: "Montserrat", sans-serif;
  font-size: .8rem;
  cursor: pointer;
  height: 1.6rem;

  &:hover {
    border-color: #111;
  }
}
select {
  height: 1.6rem;
  margin: 0 .2rem;
}
.font-small {
  font-size: 0.8rem;
}
.badge {
  text-align: center;
  border-radius: 2px;
  font-size: .8rem;
  color: white;
}

.badge-ok {
  background-color: #42b983;
}
.badge-progress {
  background-color: hsl(22, 70%, 56%);
}
.m-t-1 {
  margin-top: 1rem;
}
</style>
