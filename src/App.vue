<template>
  <div id="app">
    <h1>Countries details</h1>
    <countries-list :countries="countries"></countries-list>
    <country-details :country="selectedCountry"></country-details>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import CountriesList from './components/CountriesList.vue';
import CountryDetails from './components/CountryDetails.vue';

export default {
  name: 'App',
  data() {
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      this.countries = data;
    }),

    eventBus.$on('selected-country', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    'countries-list': CountriesList,
    'country-details': CountryDetails
  }
}
</script>

<style>

</style>
