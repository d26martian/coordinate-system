<template>
  <div class="main">
    <Home />
  </div>
</template>

<script>
import Home from '@/views/Home'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
}
.main {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.container {
  display: flex;
  flex-direction: column;
}
.row {
  display: flex;
  margin-left: -20px;
  margin-right: -20px;
}
.col {
  flex: 1;
  padding-left: 20px;
  padding-right: 20px;
}
.m-bm {
  margin-bottom: 30px;
}
</style>
