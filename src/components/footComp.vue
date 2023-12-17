<template>
    <div id="footerCompDiv">
        <div id="footerDiv">
            <div id="topFooterDiv">
                <div id="aLinkDiv">   
                    <a href="#contactTitleDiv">
                        {{ $t('footer.contact') }}
                    </a>
                    <a href="#navtop">
                        {{ $t('footer.aboutUs') }}
                    </a>
                </div>
                <div>
                    <h2>
                        {{ $t('footer.spxConseil') }}
                    </h2>
                </div>
                <div id="followUsDiv">
                    <p>
                        {{ $t('footer.followUs') }}
                    </p>
                    <a 
                    href="https://www.linkedin.com/company/spx-conseil/" target="_blank">
                        <img 
                        id="linkedinImg"
                        src="../assets/socialNetwork/linkedinLogo.webp" 
                        alt="linkedin"
                        >
                    </a>
                </div>
            </div>
            <div id="bottomFooterDiv">
                <p>
                    {{ $t('footer.sciencePoAix') }}
                </p>
                <p>
                    25 rue Gaston de Saporta 13100 Aix-en-Provence
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

#footerCompDiv {
    height: 14vh;
    background-color: #090B71;
}

#topFooterDiv {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    color: white;
    padding-top: 1vh;
}

h2 {
    font-family: 'Itim', cursive;
    margin-left: -6vh;
}

#aLinkDiv > a {
    text-decoration: none;
    color: white;
    margin-left: 2vw;
}

#linkedinImg {
    width: 50px;
    height: 50px;
    margin-top: -10px;
    margin-left: 1.2vw;
    margin-right: 0.6vw;
}

#followUsDiv {
    display: flex;
}

#bottomFooterDiv {
    color: white;
    margin-left: 2vw;
}
</style>