<template>
    <div id="downloadDiv">
        <button id="downloadButton">
            {{ $t("download.download") }}
        </button>
    </div>
</template>

<script lang="ts">
export default {

}
</script>

<style scoped>

#downloadDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 10vh;
}

#downloadButton {
    padding: 2vh 4vh;
    font-size: 22px;
    font-weight: bold;
    border-radius: 10px;
    box-shadow: 5px 5px 5px rgb(199, 199, 199);
}

#downloadButton:active {
    box-shadow: 1px 1px 5px rgb(199, 199, 199); /* Changement de l'ombre lorsqu'il est cliqué ou en focus */
}

</style>