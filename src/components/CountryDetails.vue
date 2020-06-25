<template lang="html">
    <div v-if="country">
        <h3> Country name: {{country.name}} </h3>
        <h3> {{country.name}}'s capital:{{country.capital}} </h3>
        <h3> {{country.name}}'s population {{country.population}} </h3>
        <img :src="country.flag" width="350" height="350">{{country.name}}'s flag</img>
    </div>
</template>

<script>

export default {
    name: 'country-details',
    props: ['country']
}
</script>

<style>

</style>