<template>
	<ion-page>
		<ion-header>
			<ion-toolbar>
				<ion-title>Instruções</ion-title>
			</ion-toolbar>
		</ion-header>
		<ion-content :fullscreen="true">
			<div id="container">
				<p style="margin-bottom: 8px;">
					Com esta aplicação, você pode criar uma galeria de fotos local,
					armazenando suas fotos no seu dispositivo, seja no navegador ou no seu
					dispositivo mobile com o app.
				</p>
				<p style="margin-bottom: 16px;">
					Para deletar uma foto, basta clicar em cima dela.
				</p>
				<div>
					<a
						href="https://github.com/CostaFernando/ionic-photo-gallery"
						target="_blank"
					>
						<span>Repositório</span
						><ion-icon :icon="logoGithub" size="large"></ion-icon>
					</a>
				</div>
			</div>
		</ion-content>
	</ion-page>
</template>

<script lang="ts">
import {
	IonPage,
	IonHeader,
	IonToolbar,
	IonTitle,
	IonContent,
	IonIcon,
} from "@ionic/vue";
import { logoGithub } from "ionicons/icons";

export default {
	name: "Tab1",
	components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonIcon },
	setup() {
		return { logoGithub };
	},
};
</script>

<style scoped>
#container {
	text-align: center;
	position: absolute;
	left: 0;
	right: 0;
	top: 50%;
	transform: translateY(-50%);
}

#container strong {
	font-size: 20px;
	line-height: 26px;
}

#container p {
	font-size: 16px;
	line-height: 22px;
	color: #8c8c8c;
	margin: 0;
}

#container a {
	text-decoration: none;
}
</style>
