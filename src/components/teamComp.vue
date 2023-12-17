<template>
	<div id="teamCompDiv">
		<div id="teamDiv">
			<div id="titleDiv">
				<v-icon icon="fas fa-rocket" />
				<h2>
					{{ $t('team.ourTeam') }}
				</h2>
			</div>
			<Carousel 
			:autoplay="3000"
			:transition="300"
			:settings="settings"
			:breakpoints="breakpoints"
			:wrap-around="true"
			:key="$i18n.locale">
				<Slide v-for="member in teamMembers" key="member">
					<div class="carousel__item">
						<TeamCard :name="member.name" :photoId="member.photoId" :role="member.role"/>
					</div>
				</Slide>

				<template #addons>
					<Navigation />
				</template>
			</Carousel>
		</div>
	</div>
    <div id="colorBoxDiv">
        <!-- just a colored box -->
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import TeamCard from '../components/team/teamCardComp.vue'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
	name: 'WrapAround',
	components: {
		Carousel,
		Slide,
		Navigation,
		TeamCard,
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
			teamMembers: {
				member1: {
					name: "Thomas",
					photoId: "../../src/assets/team/1-Thomas.png",
					role: 'team.president'
				},
				member2: {
					name: "Massi",
					photoId: "../../src/assets/team/2-Massi.png",
					role: 'team.vicePresident'
				},
				member3: {
					name: "Leana",
					photoId: "../../src/assets/team/3-Leana.png",
					role: 'team.generalSecretary'
				},
				member4: {
					name: "Raphaël",
					photoId: "../../src/assets/team/4-Raphaël.png",
					role: 'team.businessDevelopmentManager'
				},
				member5: {
					name: "Callista",
					photoId: "../../src/assets/team/5-Callista.png",
					role: 'team.businessDevelopmentDepartment'
				},
				member6: {
					name: "Marie",
					photoId: "../../src/assets/team/6-Marie.png",
					role: 'team.businessDevelopmentDepartment'
				},
				member7: {
					name: "Vincent",
					photoId: "../../src/assets/team/7-Vincent.png",
					role: 'team.businessDevelopmentDepartment'
				},
				member8: {
					name: "Ines",
					photoId: "../../src/assets/team/8-Ines.png",
					role: 'team.communicationManager'
				},
				member9: {
					name: "Alexis",
					photoId: "../../src/assets/team/9-Alexis.png",
					role: 'team.hrManager'
				},
				member10: {
					name: "Antoine",
					photoId: "../../src/assets/team/10-Antoine.png",
					role: 'team.treasurer'
				}
			}
		}
	}
})
</script>

<style scoped>
.carousel__item {
	height: 46vh;
	width: 31vh;
	display: flex;
	justify-content: center;
	align-items: center;
}

#teamCompDiv {
	display: flex;
	justify-content: center;
	align-items: center;
	height: 70vh;
}

#teamDiv {
	width: 90vw;
	height: 60vh;
}

#titleDiv {
	display: flex;
	align-items: center;
	height: 8vh;
}

h2 {
	margin-left: 2vw;
}

#carouselDiv {
	display: flex;
	height: 52vh;
	justify-content: center;
	align-items: center;
	border: 1px solid black;
}

#colorBoxDiv {
    height: 6vh;
    background-color: #EED0D6;
}
</style>