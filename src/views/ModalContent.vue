<!-- addNumber do funkcie dam cislo ktore sa ma pridat - toto cislo sa prida do pola -->

<template>
    <ion-page>
        <ion-content>
            <div style="color: rgb(68, 77, 99); background-color: rgb(241, 246, 255);" class="rounded-t-3xl pb-5 h-screen">
                <div class="pt-10 border-gray-400 border-b mx-5">
                    <div class="text-5xl mb-2 mr-7 text-right"> {{ mainString }} <span>{{ symbol }}</span> </div>  <!-- zmenit na string  -->
                </div>
                <div class= "mx-12">
                    <div class="flex justify-center">
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('7')">7</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('8')">8</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('9')">9</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('4')">4</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('5')">5</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('6')">6</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('1')">1</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('2')">2</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('3')">3</div>
                    </div>
                    <div class="flex justify-center">
                        <div class="text-6xl mx-12 my-5" @click="addToMainString(',')">,&nbsp;</div>
                        <div class="text-6xl mx-12 my-5" @click="addToMainString('0')">0</div>
                        <div class=" mx-12 my-auto" @click="deleteFromMainString()">
                            <svg  width="38" height="30" viewBox="0 0 38 30" xmlns="http://www.w3.org/2000/svg">
                            <g id="Vector">
                            <path class="fill-current" d="M33.625 1H13.3166C12.3004 1 11.3479 1.46716 10.703 2.28399L1.25363 14.2617C0.915212 14.6912 0.915212 15.3088 1.25363 15.7383L10.7041 27.7172C11.3478 28.533 12.3004 29 13.3166 29H33.6248C35.486 29 36.9998 27.43 36.9998 25.5V4.49999C36.9999 2.56992 35.486 1 33.625 1ZM34.7499 25.5C34.7499 26.1438 34.2456 26.6666 33.625 26.6666H13.3166C12.9772 26.6666 12.6597 26.5105 12.4454 26.2394L3.57836 14.9999L12.4443 3.76167C12.6597 3.48935 12.9771 3.33325 13.3166 3.33325H33.6248C34.2456 3.33325 34.7498 3.85624 34.7498 4.49987C34.7499 4.49999 34.7499 25.5 34.7499 25.5Z" fill="#444D63"/>
                            <path d="M26.3893 9L21.4998 13.8895L16.6103 9L14.9998 10.6105L19.8893 15.5L14.9998 20.3895L16.6103 22L21.4998 17.1105L26.3893 22L27.9998 20.3895L23.1103 15.5L27.9998 10.6105L26.3893 9Z" fill="#444D63"/>
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M9.91813 1.66429C10.7479 0.613421 11.9866 0 13.3166 0H33.625C36.0722 0 38 2.05221 37.9998 4.49999V25.5C37.9998 27.9476 36.0722 30 33.6248 30H13.3166C11.987 30 10.7479 29.387 9.91907 28.3366L0.468541 16.3576C-0.155942 15.5651 -0.1563 14.4353 0.468183 13.6428L9.91813 1.66429ZM34.7498 4.49987C34.7498 3.85624 34.2456 3.33325 33.6248 3.33325H13.3166C12.9771 3.33325 12.6597 3.48935 12.4443 3.76167L3.57836 14.9999L12.4454 26.2394C12.6597 26.5105 12.9772 26.6666 13.3166 26.6666H33.625C34.2456 26.6666 34.7499 26.1438 34.7499 25.5C34.7499 25.5 34.7499 4.49999 34.7498 4.49987ZM13.2302 25.6196C13.2595 25.6566 13.2908 25.6666 13.3166 25.6666H33.625C33.6467 25.6666 33.673 25.659 33.7003 25.6306C33.7283 25.6016 33.7499 25.5572 33.7499 25.5H34.7499C33.7499 25.5 33.7499 25.5002 33.7499 25.5L33.7498 4.50404L33.7498 4.50151C33.7498 4.50097 33.7498 4.50041 33.7498 4.49987C33.7498 4.44271 33.7282 4.3983 33.7002 4.36931C33.6729 4.34093 33.6466 4.33325 33.6248 4.33325H13.3166C13.2915 4.33325 13.2599 4.34262 13.2289 4.38167C13.2288 4.38177 13.229 4.38156 13.2289 4.38167L4.85209 14.9999L13.2302 25.6196C13.2302 25.6196 13.2301 25.6195 13.2302 25.6196ZM26.3893 8C26.6545 8 26.9089 8.10536 27.0964 8.29289L28.7069 9.90341C29.0975 10.2939 29.0975 10.9271 28.7069 11.3176L24.5246 15.5L28.7069 19.6824C29.0975 20.0729 29.0975 20.7061 28.7069 21.0966L27.0964 22.7071C26.7059 23.0976 26.0727 23.0976 25.6822 22.7071L21.4998 18.5247L17.3174 22.7071C16.9269 23.0976 16.2938 23.0976 15.9032 22.7071L14.2927 21.0966C14.1052 20.9091 13.9998 20.6547 13.9998 20.3895C13.9998 20.1243 14.1052 19.8699 14.2927 19.6824L18.4751 15.5L14.2927 11.3176C13.9022 10.9271 13.9022 10.2939 14.2927 9.90341L15.9032 8.29289C16.2938 7.90237 16.9269 7.90237 17.3174 8.29289L21.4998 12.4753L25.6822 8.29289C25.8697 8.10536 26.1241 8 26.3893 8ZM21.4998 13.8895L16.6103 9L14.9998 10.6105L19.8893 15.5L14.9998 20.3895L16.6103 22L21.4998 17.1105L26.3893 22L27.9998 20.3895L23.1103 15.5L27.9998 10.6105L26.3893 9L21.4998 13.8895ZM10.703 2.28399C11.3479 1.46716 12.3004 1 13.3166 1H33.625C35.486 1 36.9999 2.56992 36.9998 4.49999V25.5C36.9998 27.43 35.486 29 33.6248 29H13.3166C12.3004 29 11.3478 28.533 10.7041 27.7172L1.25363 15.7383C0.915212 15.3088 0.915212 14.6912 1.25363 14.2617L10.703 2.28399Z" fill="#444D63"/>
                            </g>
                            </svg>
                        </div>
                    </div>
                </div>
                <div style="background-color: rgb(65, 187, 249); box-shadow: 0px 4px 4px 0px rgba(20, 119, 174, 0.25);" class="text-center mx-5 py-3.5 mt-2 rounded-3xl">
                    <button class="font-bold text-white" @click="doneButton()">Hotovo</button>
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
    props: {
        symbol: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            mainString: '',
        }
    },
    methods: {
        addToMainString(value: string){
            if (this.mainString === '0' && value === '0') {
                console.log ("two zeros cannot be at the beginning ")
                return
            }
            if (this.mainString === '' && value === ',') {
                console.log("comma cannot be at the beginning ")
                return
            }
            if (this.mainString.includes(',') && value === ',') {
                console.log("two commas can not be in one string")
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
        }
    },
}
</script>

