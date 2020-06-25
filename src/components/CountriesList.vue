<template lang="html">
    <select v-on:change="handleChange" v-model="selectedCountry">
        <option v-for="(country, index) in countries" :key="index" :value="country">{{country.name}}</option>
    </select>
</template>

<script>
import {eventBus} from '../main.js';

export default {
    name: 'countries-list',
    props: ['countries'],
    
    data() {
        return {
            selectedCountry: null
        }
    },
    methods: {
        handleChange: function () {
            eventBus.$emit('selected-country', this.selectedCountry)
        }
    }
}
</script>

<style>

</style>