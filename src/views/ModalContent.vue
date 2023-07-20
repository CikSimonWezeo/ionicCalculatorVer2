<!-- addNumber do funkcie dam cislo ktore sa ma pridat - toto cislo sa prida do pola -->

<template>
    <ion-page>
        <ion-content>
            <div class="text-black bg-white rounded-t-3xl pb-5">
                <div class="border-b-2 mx-3 pt-5">
                    <div class="text-5xl mb-2 mr-7 text-right">{{ mainString }} <span>€</span> </div>  <!-- zmenit na string  -->
                </div>
                <div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="numberSeven()">7</div>
                        <div class="text-7xl mx-12 my-4" @click="numberEight()">8</div>
                        <div class="text-7xl mx-12 my-4" @click="numberNine()">9</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="numberFour()">4</div>
                        <div class="text-7xl mx-12 my-4" @click="numberFive()">5</div>
                        <div class="text-7xl mx-12 my-4" @click="numberSix()">6</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="numberOne()">1</div>
                        <div class="text-7xl mx-12 my-4" @click="numberTwo()">2</div>
                        <div class="text-7xl mx-12 my-4" @click="numberThree()">3</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="characterComma()">,</div>
                        <div class="text-7xl mx-12 my-4" @click="numberZero()">0</div>
                        <div class="text-7xl mx-12 my-4" @click="deleteButton()">x</div> <!-- tu bude svg -->
                    </div>
                </div>
                <div class="text-center">
                    <button class="text-2xl font-bold text-white bg-blue-500 px-32 py-2 rounded-3xl" @click="doneButton()">Hotovo</button>
                </div>
            </div>
        </ion-content>
    </ion-page>
</template>
<script lang="ts">
import { IonPage, IonContent } from '@ionic/vue';
export default {
    components: {
        IonPage,
        IonContent,
    },
    data() {
        return {
            mainString: "45,00"
        }
    },
    methods: {
        numberSeven() {
            console.log("7")
            this.mainString.concat("7")
        },
        numberEight() {
            console.log("8")
        },
        numberNine() {
            console.log("9")
        },
        numberFour() {
            console.log("4")
        },
        numberFive() {
            console.log("5")
        },
        numberSix() {
            console.log("6")
        },
        numberOne() {
            console.log("1")
        },
        numberTwo() {
            console.log("2")
        },
        numberThree() {
            console.log("3")
        },
        characterComma() {
            console.log(",")
        },
        numberZero() {
            console.log("0")
        },
        deleteButton() {
            console.log("x")
        },
        doneButton() {
            console.log("Hotovo")
        }
    },
}
</script>

<style scoped>
   .main-height{
        height: 75vh;
   }
</style>