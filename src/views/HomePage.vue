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
            <div class="text-3xl mt-16">
                hodnota kalkulacky: {{ fromCalculator }}
            </div>
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
            toCalculator: '',
            fromCalculator: '',
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
            this.toCalculator = "1000"
            const modal = await modalController.create({
                component: ModalContent,
                componentProps: {
                    symbol: this.symbol, // Pass the "symbol" as a prop to ModalContent.vue
                    toCalculator: this.toCalculator
                },
                breakpoints: [0, 0.65],
                initialBreakpoint: 0.65,
            });
            modal.present();
            const { data, role } = await modal.onWillDismiss();

            if (role === 'done') {
                this.fromCalculator = `${data}`;
            }
            
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

