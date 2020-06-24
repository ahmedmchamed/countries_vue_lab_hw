<template>
    <ul>
        <countries-list-items v-for="(country, index) in countries" :key="index" :country="country"></countries-list-items>
    </ul>
</template>

<script>
import CountriesListItems from './CountriesListItems.vue';

export default {
    name: 'countries-list',
    props: ['countries'],
    components: {
        'countries-list-items': CountriesListItems
    }
}
</script>

<style>

</style>