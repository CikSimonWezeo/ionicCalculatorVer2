
<template>
    <ion-page>
        <ion-content>
            <div style="color: rgb(68, 77, 99); background-color: rgb(241, 246, 255);" class="rounded-t-3xl pb-5 h-screen">
                <div class="pt-10 border-gray-400 border-b mx-5">
                    <div class="text-5xl mb-2 mr-7 text-right"> {{ mainString }} <span>{{ symbol }}</span> </div>  <!-- zmenit na string  -->
                </div>
                <div class= "text-center mt-4 mx-3 mb-5">
                    <div class="flex w-full justify-between">
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('7')">7</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('8')">8</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('9')">9</div>
                    </div>
                    <div class="flex  w-full justify-between">
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('4')">4</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('5')">5</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('6')">6</div>
                    </div>
                    <div class="flex w-full justify-between">
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('1')">1</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('2')">2</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('3')">3</div>
                    </div>
                    <div class="flex w-full justify-between">
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString(',')">,</div>
                        <div class="text-6xl w-1/3 my-4" @click="addToMainString('0')">0</div>
                        <div class=" w-1/3 self-center" @click="deleteFromMainString()">
                            <img class="w-11 mx-auto" src="./Vector.svg" alt="">
                        </div>
                    </div>
                </div>
                <div style="background-color: rgb(65, 187, 249); box-shadow: 0px 4px 4px 0px rgba(20, 119, 174, 0.25);" class="text-center mx-6 py-3.5 mt-2 mb-5 rounded-3xl">
                    <button class="font-bold text-white text-xl" @click="doneButton()" :strong="true">Hotovo</button>
                </div>
            </div>
        </ion-content>
    </ion-page>
</template>
<script lang="ts">
import { IonPage, IonContent, modalController } from '@ionic/vue';
export default {
    components: {
        IonPage,
        IonContent,
    },
    props: {
        symbol: {
            type: String,
            required: true
        },
        toCalculator: {
            type: String,
            required: true
        },
    },
    data() {
        return {
            mainString: '',
            decimalsCounter: 0

        }
    },
    created() {
        this.mainString = this.toCalculator
    },
    methods: {
        addToMainString(value: string){
            if (this.mainString === '0' && value === '0') {
                console.log ("two zeros cannot be at the beginning ")
                return
            }
            if (this.mainString === '' && value === ',') {
                this.mainString = '0,'
                console.log("zero and comma added")
                return
            }
            if (this.mainString.includes(',') && value === ',') {
                console.log("two commas can not be in one string")
                return
            }
            if (this.mainString.includes(',')) {
                this.decimalsCounter += 1
            }
            if (this.decimalsCounter > 2) {
                return
            }
            this.mainString += value
            console.log(value)
        },
        deleteFromMainString(){
            this.mainString = this.mainString.slice(0, -1)
            console.log(this.mainString)
        },
        doneButton(){
            console.log(this.mainString)
            var mainNumber = Number(this.mainString)
            console.log(mainNumber)
            return modalController.dismiss(mainNumber, 'done');

        },
    },
}
</script>
