<!-- naastudovat si komponenty vue -->


<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>App</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            <p class="font-bold text-red-400" >TailWind</p>
            <ion-button id="open-modal" expand="block" @click="openModal">Open Sheet Modal</ion-button>
        </ion-content>
    </ion-page>    
</template>

<script lang="ts">
import { IonButton, IonModal, IonHeader, IonContent, IonToolbar, IonTitle, IonLabel, modalController, IonPage } from '@ionic/vue';
import ModalContent from './ModalContent.vue';

export default {
    components: {
    IonButton,
    IonModal,
    IonHeader,
    IonContent,
    IonToolbar,
    IonTitle,
    IonLabel,
    IonPage
},
    methods: {
        async openModal() {
            const modal = await modalController.create({
                component: ModalContent,
            });
            modal.present();
        },
    },
};
</script>