<!-- addNumber do funkcie dam cislo ktore sa ma pridat - toto cislo sa prida do pola -->

<template>
    <ion-page>
        <ion-content>
            <div class="text-black bg-white rounded-t-3xl pb-5">
                <div class="border-b-2 mx-3 pt-5">
                    <div class="text-5xl mb-2 mr-7 text-right"> {{ mainString }} <span>€</span> </div>  <!-- zmenit na string  -->
                </div>
                <div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('7')">7</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('8')">8</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('9')">9</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('4')">4</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('5')">5</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('6')">6</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('1')">1</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('2')">2</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('3')">3</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-7xl mx-12 my-4" @click="addToMainString(',')">,</div>
                        <div class="text-7xl mx-12 my-4" @click="addToMainString('0')">0</div>
                        <div class="text-7xl mx-12 my-4" @click="deleteFromMainString()">x</div> <!-- tu bude svg -->
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
            mainString: '',
        }
    },
    methods: {
        addToMainString(value: string){
            this.mainString += value
            console.log(value)
        },
        deleteFromMainString(){
            this.mainString = this.mainString.slice(0, -1)
            console.log(this.mainString)
        },
        doneButton(){
            console.log(this.mainString)
        }
    },
}
</script>

<style scoped>
   .main-height{
        height: 75vh;
   }
</style>