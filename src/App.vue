<template>
    <div class="app">
      <NavBar/>
      <router-view />
    </div>
</template>

<script>
import NavBar from "./components/NavBar.vue"
import CountriesList from "./components/CountriesList.vue"

export default {
  name: "App",
  components: {
    NavBar,
    CountriesList
  },
  data() {
    
  }
}
</script>

<style>

</style>