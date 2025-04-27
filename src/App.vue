<template>

    <div class="row">

        <div class="col col-4"></div>

        <div class="col col-4">

            <SearchBar/>

            <ResultsSet/>

        </div>

    </div>

</template>

<script>
    import SearchBar from './components/SearchBar.vue'
    import ResultsSet from './components/ResultsSet.vue'

    export default {
        name: 'App',
        components: {
            SearchBar,
            ResultsSet
        }
    }
</script>

<style>
    #app {
        font-family: Helvetica, Arial, sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        margin-top: 20px;
}
</style>
