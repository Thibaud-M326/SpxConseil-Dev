<template>
    <Navtop />
    <About />
    <History />
    <Download />
    <Team />
    <Contact />
    <!-- <Partners />
    <Foot /> -->
</template>

<script lang="ts">
import Navtop from '../components/navtopComp.vue'
import About from '../components/aboutComp.vue'
import History from '../components/historyComp.vue'
import Download from '../components/downloadComp.vue'
import Team from '../components/teamComp.vue'
import Contact from '../components/contactComp.vue'
import Partners from '../components/partnersComp.vue'
import Foot from '../components/footComp.vue'

export default {
    components: {
        Navtop,
        About,
        History,
        Download,
        Team,
        Contact,
        Partners,
        Foot,
    }
}
</script>

<style scoped>

</style>