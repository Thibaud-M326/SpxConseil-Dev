<template>
    <div id="partnersCompDiv">
        <div id="partnersDiv">
            <div id=titleDiv>
                <v-icon icon="fas fa-handshake" />
                <h2>
                    {{ $t('partners.partners') }}
                </h2>
            </div>
            <Carousel id="carousel" :autoplay="3000" :transition="300" :settings="settings" :breakpoints="breakpoints" :wrap-around="true"
                :key="$i18n.locale">
                <Slide v-for="partner in partners" key="member">
                    <div class="carousel__item">
                        <img id="carouselImg" :src="partner.photoUrl" :alt="partner.alt">
                    </div>
                </Slide>

                <template #addons>
                    <Navigation />
                </template>
            </Carousel>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
    name: 'WrapAround',
    components: {
        Carousel,
        Slide,
        Navigation,
    },
    data() {
        return {
            settings: {
                itemsToShow: 1,
                snapAlign: 'center'
            },
            breakpoints: {
                700: {
                    itemsToShow: 2,
                    snapAlign: 'center',
                },
                1024: {
                    itemsToShow: 3,
                    snapAlign: 'center',
                }
            },
            partners: {
                partner1: {
                    photoUrl: "../../src/assets/partners/arcelorMittal.png",
                    alt: "Arcelor Mittal"
                },
                partner2: {
                    photoUrl: "../../src/assets/partners/cea.png",
                    alt: "CEA"
                },
                partner3: {
                    photoUrl: "../../src/assets/partners/CMA_CGM.png",
                    alt: "CMA CGM"
                },
                partner4: {
                    photoUrl: "../../src/assets/partners/hautConseilClimat.jpg",
                    alt: "Haut Conseil Climat"
                },
                partner5: {
                    photoUrl: "../../src/assets/partners/havas360.png",
                    alt: "Havas360"
                },
                partner6: {
                    photoUrl: "../../src/assets/partners/mendo.jpg",
                    alt: "Mendo"
                },
                partner7: {
                    photoUrl: "../../src/assets/partners/regionPACA.png",
                    alt: "Region PACA"
                },
                partner8: {
                    photoUrl: "../../src/assets/partners/sciencePoAix.png",
                    alt: "SciencesPo-Aix"
                },
            }
        }
    }
})
</script>

<style scoped>
#partnersCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 68vh;
}

#partnersDiv {
    width: 90vw;
    height: 50vh;
    margin-bottom: 6vh;
}

#titleDiv {
    display: flex;
    align-items: center;
    height: 8vh;
    margin-bottom: 2vh;
}

h2 {
    margin-left: 2vw;
}

#carousel {
    border-radius: 7px;
    box-shadow: 0px 0px 10px #e9e9e9;
}
.carousel__item {
    height: 42vh;
    width: 37vw;
    display: flex;
    justify-content: center;
    align-items: center;
}

#carouselImg {
    width: 28vh;
    height: 28vh;
    object-fit: contain;
}
</style>