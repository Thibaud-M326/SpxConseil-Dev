<template>
    <div id="teamCardCompDiv">
        <div id="teamCardDiv">
            <div id="teamImgDiv">
                <img
                    id="teamImg"
                    :src="photoId"
                    alt="TeamPicture"
                >
            </div>
            <div id="teamNameP">
                <p>
                    {{ name }}
                </p>
                <p>
					{{ $t(role!) }}
                </p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        name: String,
        photoId: String,
        role: String,
    },
}
</script>

<style scoped>

#teamCardCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 44vh;
    width: 30vh;
    border-radius: 15px;
    box-shadow: 1px 1px 10px rgb(196, 196, 196);
}

#teamCardDiv {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

#teamImgDiv {
    display: flex;
    height: 32vh;
}

#teamImg {
    height: 30vh;
    width: 22vh;
    object-fit: cover;
    border-radius: 5px;
}

#teamNameP {
    display: flex;
    flex-direction: column;
    font-weight: bold;
}
</style>