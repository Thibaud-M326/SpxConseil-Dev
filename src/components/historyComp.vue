<template>
    <div id="historyCompDiv">
        <div id="historyDiv">
            <div id="historyTextDiv">
                <h2
                id="historyH2"
                >
                {{ $t("history.historyTitle") }}
                </h2>
                <p
                id="historyP"
                >
                {{ $t("history.historyText") }}
                </p>
            </div>
        </div>
        <div id="masterDiv">
            <div id="masterTextDiv">
                <h2
                id="masterH2"
                >
                {{ $t("history.masterTitle") }}
                </h2>
                <p
                id="masterP"
                >
                {{ $t("history.masterText") }}
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

#historyCompDiv {
    display:flex;
    flex-direction: column;
    justify-content: space-evenly;
    height: 80vh;
}

#historyDiv {
    align-self: flex-start;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #080A70;
    color: white;
    height: 33vh;
    width: 70vw;
    border-top-right-radius: 100px;
    border-bottom-right-radius: 100px;
}

#historyTextDiv {
    width: 60vw;
    overflow: auto;
}

h2 {
    margin-bottom: 1vh;
}

p {
    font-size: large
}

#masterDiv {
    align-self: flex-end;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #AB0200;
    color: white;
    white-space: pre-line;
    height: 33vh;
    width: 70vw;
    padding-left: 5vw;
    border-top-left-radius: 100px;
    border-bottom-left-radius: 100px;
}

#masterTextDiv {
    width: 60vw;
    overflow: auto;
}
</style>