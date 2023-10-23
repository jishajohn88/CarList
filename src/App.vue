<template>
  <Sidebar />
  <Header/>
  <ListingFeed />
</template>
<script>
import ListingFeed from './components/ListingFeed.vue'
import Sidebar from './components/Sidebar.vue'
import Header from './components/Header.vue'
export default {
  components: {
    ListingFeed,
    Sidebar,
    Header
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
}
*{
  margin :0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira sans', sans-serif;
}
body {
  margin:0;
  background: #eee;
}
</style>
