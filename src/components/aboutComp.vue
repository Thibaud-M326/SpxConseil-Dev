<template>
    <div>
        <div id="cityBackgroundDiv">
            <v-parallax
            id="cityBackgroundImg"
            src="src/assets/SpxConseil/cityBackgroundDallE.png" 
            ></v-parallax>
        </div>
        <div id="aboutDiv">
            <div id="aboutTextDiv">
                <h2
                id="overviewH2"
                >
                {{ $t("about.overview") }}
                </h2>
                <p
                id="textP"
                > 
                {{ $t("about.text") }}
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

#cityBackgroundImg {
    width: 100%;
    height: 66vh;
    object-fit: cover;
    position: absolute; 
    z-index: -1;
}

#aboutDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 66vh;
}

#aboutTextDiv {
    background-color: #f0f4f7c7;
    width: 66vw;
    max-height: 60vh;
    overflow: auto;
}

#overviewH2 {
    margin-bottom: 1vh;
}

#textP {
    font-size: large;
}


</style>