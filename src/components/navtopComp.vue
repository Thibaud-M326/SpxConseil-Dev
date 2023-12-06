<template>
    <div id="navtop">
        <div>
            <h1
            id="spxConseilH1"
            >
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
            href="/"
            >
                contact
            </a>
            <p id="separatorDiv"></p>
            <a 
            href="/">
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
                console.log('Anglais choisi')
                this.$i18n.locale = "en"
            } else {
                console.log('français choisi')
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

#navtopRightDiv {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

#spxConseilH1 {
    font-size: 1.5rem;
    margin: 1vh;
    margin-left: 3vw;
}

#aboutUsA {
    font-size: 1rem;
    color: black;
    text-decoration: none;
    margin: 1vh;
}

#contactA {
    font-size: 1rem;
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
    font-size: 0.9rem;
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

</style>
