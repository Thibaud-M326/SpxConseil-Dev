<template>
    <div id="teamCompDiv">
        <div id="teamDiv">
            <div id="titleDiv">
                <v-icon icon="fas fa-rocket" />
                <h2>
                    {{ $t('team.ourTeam') }}
                </h2>
            </div>
            <div id="carouselDiv">
                
            </div>
        </div>
    </div>


</template>

<script lang="ts">
import TeamCard from '../components/team/teamCardComp.vue'

export default {
    components: {
        TeamCard
    },
    data() {
        return {
            slides: [
                '1',
                '2',
                '3',
            ]
        }
    }
}
</script>

<style scoped>

#teamCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 70vh;
}

#teamDiv {
    width: 90vw;
    height: 60vh;
}

#titleDiv {
    display: flex;
    align-items: center;
    height: 8vh;
}

h2 {
    margin-left: 2vw;
}

#carouselDiv {
    display: flex;
    height: 52vh;
    justify-content: center;
    align-items: center;
    border: 1px solid black;
}

</style>