<script>
import Header from './components/Header.vue'
import Home from './pages/Home.vue'
import Quote from './pages/Quote.vue'
import Calc from './pages/Calc.vue'
export default {
    data() {
        return {
            page: 0
        }
    },
    components: {
        Header,Home, Quote, Calc
    },
    methods: {
        changePage(page) {
            console.log(page)
            this.page = page
        }
    }
    // ...
}

// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
    <header>
        <Header :changePage="changePage"/>
    </header>

    <main>
        <Home v-if="page === 0"/>
        <Calc v-else-if="page === 1"/>
        <Quote v-else-if="page === 2"/>
    </main>
</template>

<style scoped>
    main {
        padding-top: 25px;
        min-height: 95vh;
        background-color: #e0dbb1;
    }
</style>

