<template>
    <div id="navtop">
        <div>
            <h1
            id="spxConseilH1"
            >
                Spx Conseil
            </h1>
        </div>
        <div>
            <a 
            id="aboutUsA" 
            href="/"
            >
                à notre propos
            </a>
            <a 
            id="contactA" 
            href="/"
            >
                contact
            </a>
            <a 
            id="linkedinA" 
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
            } else {
                console.log('français choisi')
            }
        }
    }
}
</script>

<style scoped>

#navtop {
    display: flex;
    flex-direction: row;
    align-items: baseline;
    justify-content: space-between;
    border-bottom: 1px solid black;
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
    color: black;
    text-decoration: none;
    margin: 1vh;
}

#linkedinA {
    margin: 1rem;
}

#linkedinImg {
    width: 5vh;
    height: 5vh;
    margin-bottom: -1.9vh;
}

#buttonDiv {
    font-size: 1rem;
    width: 60px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: 1vh;
    margin-right: 3vw;
}

#langColorBlack {
    color: black
}

#langColorGrey {
    color: grey
}

</style>
