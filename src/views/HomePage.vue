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
            <ion-button id="open-modal" expand="block" @click="openModalEuro">Open Sheet Modal-Euro</ion-button>
            <ion-button id="open-modal" expand="block" @click="openModalKc">Open Sheet Modal-Kc</ion-button>

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
    data() {
        return {
            symbol: '',
        }
    },
    methods: {
        async openModal() {
            const modal = await modalController.create({
                component: ModalContent,
                componentProps: {
                    symbol: this.symbol // Pass the "symbol" as a prop to ModalContent.vue
                },
                breakpoints: [0, 0.65], 
                initialBreakpoint: 0.65,
            });
            modal.present();
        },
        async openModalEuro() {
            this.symbol = "e"
            const modal = await modalController.create({
                component: ModalContent,
                componentProps: {
                    symbol: this.symbol // Pass the "symbol" as a prop to ModalContent.vue
                },
                breakpoints: [0, 0.65],
                initialBreakpoint: 0.65,
            });
            modal.present();
        },
        async openModalKc() {
            this.symbol = "Kc"
            const modal = await modalController.create({
                component: ModalContent,
                componentProps: {
                    symbol: this.symbol // Pass the "symbol" as a prop to ModalContent.vue
                },
                breakpoints: [0, 0.65],
                initialBreakpoint: 0.65,
            });
            modal.present();
        },
    },
};
</script>

