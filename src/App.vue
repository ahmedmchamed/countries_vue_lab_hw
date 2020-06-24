<template>
  <div id="app">
    <countries-list :countries="countries"></countries-list>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';

export default {
  name: 'App',
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      this.countries = data;
    })
  },
  data() {
    return {
      countries: []
    }
  },
  components: {
    'countries-list': CountriesList
  }
}
</script>

<style>

</style>
