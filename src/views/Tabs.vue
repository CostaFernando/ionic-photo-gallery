<template>
	<ion-page>
		<ion-tabs>
			<ion-tab-bar slot="bottom">
				<ion-tab-button tab="tab2" href="/tabs/tab2">
					<ion-icon :icon="images" />
					<ion-label>Fotos</ion-label>
				</ion-tab-button>

				<ion-tab-button tab="tab1" href="/tabs/tab1">
					<ion-icon :icon="triangle" />
					<ion-label>Instruções</ion-label>
				</ion-tab-button>
			</ion-tab-bar>
		</ion-tabs>
	</ion-page>
</template>

<script lang="ts">
import {
	IonTabBar,
	IonTabButton,
	IonTabs,
	IonLabel,
	IonIcon,
	IonPage,
} from "@ionic/vue";
import { images, square, triangle } from "ionicons/icons";

export default {
	name: "Tabs",
	components: { IonLabel, IonTabs, IonTabBar, IonTabButton, IonIcon, IonPage },
	setup() {
		return {
			images,
			square,
			triangle,
		};
	},
};
</script>
