<template>
  <h1 class="app-title">Kitty Rolodex</h1>
  <input class="search-box" type="search" v-model="searchTerm" placeholder="Search Kitty" >
  <CardList :profiles="filterCards" />

</template>

<script>
import { CardList} from './components'



export default {
  name: 'App',
  components: {
    CardList
  },

  created() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(res => res.json())
      .then(data => this.profiles = data)
  },

  data() {
    return {
      profiles: [],
      filteredProfiles: [],
      searchTerm: ''
    }
  },

  computed: {
    filterCards() {
      return this.filteredProfiles = this.profiles.filter(profile => (profile.name.toLocaleLowerCase()).includes(this.searchTerm))
    }

  }

}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(to left,
      rgb(248, 248, 248) 0%,
      rgb(85, 155, 212) 100%);
  text-align: center;
}

.app-title {
  margin-top: 75px;
  margin-bottom: 50px;
  font-size: 76px;
  color: rgb(121, 12, 125);
  font-family: Cinzel;

}

.search-box {
  border: none;
  outline: none;
  padding: 10px;
  width: 150px;
  line-height: 30px;
  margin-bottom: 30px;
}
</style>
