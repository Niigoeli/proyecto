<script setup>
import { ref } from "vue";
let name = ref("hola");
let band = ref(" hhh");

let showH = ref(false);
let showK = ref(false);
let showS = ref(false);

function h() {
    console.log("clicked");
    showH.value = true;
    showK.value = false;
    showS.value = false;
}

function k() {
    console.log("clicked");
    showH.value = false;
    showK.value = true;
    showS.value = false;
}

function s() {
    console.log(" clicked");
    showH.value = false;
    showK.value = false;
    showS.value = true;
}

</script>

<template>
    <div class="flex justify-center items-center h-[729px] bg-zinc-900 ">
        <div class="bg-black text-white p-7 rounded-3xl shadow-2xl shadow-white">
            <div class="m-1 ">
                <button @click="h"
                    class="px-3 py-1 mx-2 border border-white transition hover:bg-white hover:text-black">H</button>
                <button @click="k"
                    class="px-3 py-1 mx-2 border border-white  transition hover:bg-white hover:text-black">K</button>
                <button @click="s"
                    class="px-3 py-1  mx-2 border border-white  transition hover:bg-white hover:text-black">S</button>
            </div>
            <div>
                <img src="https://i.pinimg.com/originals/fc/89/02/fc890248c339ba50190a3a504b879d40.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showH">

                <img src="https://i.pinimg.com/originals/fc/89/02/fc890248c339ba50190a3a504b879d40.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showK">


                <img src="https://i.pinimg.com/originals/fc/89/02/fc890248c339ba50190a3a504b879d40.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showS">
            </div>
            <div class=" flex flex-col justify-center items-center pb-3">
                <p class="mt-4 flex">Name: {{ name }}</p>
                <p class="flex">Band: {{ band }}</p>
            </div>
        </div>
    </div>

</template>

