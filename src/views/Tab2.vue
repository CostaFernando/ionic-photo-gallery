<template>
	<ion-page>
		<ion-header>
			<ion-toolbar>
				<ion-title>Galeria de fotos</ion-title>
			</ion-toolbar>
		</ion-header>
		<ion-content :fullscreen="true">
			<ion-grid>
				<ion-row>
					<ion-col size="12" sizeSm="4" :key="photo" v-for="photo in photos">
						<ion-img
							:src="photo.webviewPath"
							@click="showActionSheet(photo)"
						></ion-img>
					</ion-col>
				</ion-row>
			</ion-grid>

			<ion-fab vertical="bottom" horizontal="center" slot="fixed">
				<ion-fab-button @click="takePhoto()">
					<ion-icon :icon="camera"></ion-icon>
				</ion-fab-button>
			</ion-fab>
		</ion-content>
	</ion-page>
</template>

<script lang="ts">
import { camera, trash, close } from "ionicons/icons";
import {
	IonPage,
	IonHeader,
	IonFab,
	IonFabButton,
	IonIcon,
	IonToolbar,
	IonTitle,
	IonContent,
	IonGrid,
	IonRow,
	IonCol,
	IonImg,
	actionSheetController,
} from "@ionic/vue";

import { usePhotoGallery, Photo } from "@/composables/usePhotoGallery";

export default {
	name: "Tab2",
	components: {
		IonPage,
		IonHeader,
		IonFab,
		IonFabButton,
		IonIcon,
		IonToolbar,
		IonTitle,
		IonContent,
		IonGrid,
		IonRow,
		IonCol,
		IonImg,
	},
	setup() {
		const { photos, takePhoto, deletePhoto } = usePhotoGallery();

		const showActionSheet = async (photo: Photo) => {
			const actionSheet = await actionSheetController.create({
				header: "Fotos",
				buttons: [
					{
						text: "Deletar",
						role: "destructive",
						icon: trash,
						handler: () => {
							deletePhoto(photo);
						},
					},
					{
						text: "Cancelar",
						icon: close,
						role: "cancel",
					},
				],
			});

			await actionSheet.present();
		};

		return { photos, takePhoto, showActionSheet, camera, trash, close };
	},
};
</script>
