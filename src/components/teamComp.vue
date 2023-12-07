<template>
    <div id="teamCompDiv">
        <div id="teamDiv">
            <div id="titleDiv">
                <v-icon icon="fas fa-rocket" />
                <h2>
                    Notre Equipe :
                </h2>
            </div>
            <div id="carousselDiv">
                <p>
                    caroussel
                </p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

export default {

}
</script>

<style scoped>

#teamCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 70vh;
    background-color: rgb(202, 255, 255);
}

#teamDiv {
    width: 90vw;
    height: 60vh;
    background-color: rgb(250, 255, 202);
}

#titleDiv {
    display: flex;
    align-items: center;
    height: 8vh;
    background-color: aquamarine;
}

h2 {
    margin-left: 2vw;
}

#carousselDiv {
    display: flex;
    height: 52vh;
    justify-content: center;
    align-items: center;
    background-color: rgb(215, 172, 255);
}
</style>