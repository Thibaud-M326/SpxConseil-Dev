<template>
    <div id="teamCardCompDiv">
        <div id="teamCardDiv">
            <div id="teamImgDiv">
                <!-- <img :src="pictureSrc" alt=""> -->
                <img
                    id="teamImg"
                    src="../../assets/team/1-Thomas-PRESIDENT.png" 
                    alt=""
                >
            </div>
            <div id="teamNameP">
                <p>
                    Thomas
                </p>
                <p>
                    PRESIDENT
                </p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        slide: String,
    },
    data() {
        return {
            pictureSrc: ''
        }
    },
    methods: {
        findPictureSrc() {
            this.pictureSrc = "../../assets/SpxConseil/spxLogo.jpg"
        }
    },
    mounted() {
        this.findPictureSrc
    }
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
    box-shadow: 1px 1px 10px grey;
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
    align-items: center;
    font-weight: bold;
}
</style>