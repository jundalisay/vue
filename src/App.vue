<template>
  <div id="app">
    <div :class="isOnline ? 'green' : 'red'">
      SORA Food
      <b>{{ isOnline ? 'is Online': 'is Offline' }} </b>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/posts">Posts</router-link> |
      <router-link to="/photos">Photos</router-link>
    </div>
    <router-view/>
  </div>
</template>
<script>
export default {
  data () {
    return {
      isOnline: window.navigator.onLine
    }
  },
  created () {
    window.
    window.addEventListener('online', () => (this.isOnline = true))
    window.addEventListener('offline', () => (this.isOnline = false))
  }
}
</script>
<style>
body {
  margin: 0;
}
.green {
  color: #fff;
  padding: 5px;
  background-color: #00ceb4;
}

.red {
  color: #fff;
  padding: 5px;
  background-color: tomato;
}

#app {
  font-family: 'Cabin', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #e0f3ff;
  /*background: url('https://sorasystem-cdn.sirv.com/phones1200.jpg') no-repeat;
  background-size: 100%;*/
}

#nav {
  padding: 30px;
  background: #008be3;
}

#nav a {
  font-weight: bold;
  color: #fff;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
