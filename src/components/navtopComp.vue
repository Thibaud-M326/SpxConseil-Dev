<template>
    <div id="navtop">
        <div id="logoTitleDiv">
            <img id="spxConseilImg" src="../assets/SpxConseil/spxLogo.jpg" alt="Spx Conseil Logo">
            <h1 id="spxConseilH1">
                Spx Conseil
            </h1>
        </div>
        <div id="navtopRightDiv">
            <a 
            id="aboutUsA" 
            href="/"
            >
                {{ $t("navtop.aboutUs") }}
            </a>
            <a 
            id="contactA" 
            href="#contactTitleDiv"
            >
                contact
            </a>
            <p id="separatorDiv"></p>
            <a 
            href="https://www.linkedin.com/company/spx-conseil/" target="_blank">
                <img 
                id="linkedinImg"
                src="../assets/socialNetwork/linkedinLogo.webp" 
                alt="linkedin"
                >
            </a>
            <button @click="chooseLang">
                <div id="buttonDiv">
                    <div
                    :id="langEN"
                    >
                        EN
                    </div>
                    /
                    <div
                    :id="langFR"
                    >
                        FR 
                    </div>
                </div>
            </button>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    data() {
        return {
            langEN: 'langColorBlack',
            langFR: 'langColorGrey',
        }
    },
    methods: {
        chooseLang() {    
            this.changeColor()
            this.changeLang()
        },
        changeColor() {
            if(this.langEN == 'langColorBlack') {
                this.langEN = 'langColorGrey'
                this.langFR = 'langColorBlack'
            } else {
                this.langEN = 'langColorBlack'
                this.langFR = 'langColorGrey'
            }
        },
        changeLang() {
            if(this.langEN == 'langColorBlack') {
                this.$i18n.locale = "en"
            } else {
                this.$i18n.locale = "fr"
            }
        }
    }
}
</script>

<style scoped>

#navtop {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid black;
    height: 4rem;
}

#logoTitleDiv {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

#spxConseilImg {
    width: 6vw;
    height: 6vw;
    margin-left: 2vw;
    margin-top: 7vh;
}

#spxConseilH1 {
    font-family: 'Itim', cursive;
    font-size: max(1.5vw, 19px);
    margin-left: 2vw;
}

#navtopRightDiv {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

#aboutUsA {
    font-size: max(1vw, 12px);
    color: black;
    text-decoration: none;
    margin: 1vh;
}

#contactA {
    font-size: max(1vw, 12px);
    text-decoration: none;
    margin: 1vh;
    margin-right: 2vw;
    color: black;
}

#separatorDiv {
    width: 1px;
    height: 40px;
    background-color: black;
}

#linkedinImg {
    width: 50px;
    height: 50px;
    margin-bottom: -5px;
    margin-left: 1.2vw;
    margin-right: 0.6vw;
}

#buttonDiv {
    font-size: max(0.9vw, 12px);
    width: 60px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: 1vh;
    margin-right: 3vw;
    margin-left: 0;
}

#langColorBlack {
    color: black
}

#langColorGrey {
    color: grey
}

@media only screen and (max-width: 850px) {
    #spxConseilImg {
        margin-top: 0vh;
    }
}
</style>
