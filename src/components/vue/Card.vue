<script setup>
import { ref } from "vue";
let name = ref("");
let band = ref("");

let showH = ref(false);
let showK = ref(false);
let showS = ref(false);
let logo = ref(true);

function h() {
    console.log("clicked");
    name = "Hayate";
    band = "UniChord";
    showH.value = true;
    showK.value = false;
    showS.value = false;
    logo.value = false;
}

function k() {
    console.log("clicked");
    name = "Kurumi";
    band = "Lyrical Lily";
    showH.value = false;
    showK.value = true;
    showS.value = false;
    logo.value = false;
}

function s() {
    console.log(" clicked");
    name = "Sophia";
    band = "Abyssmare";
    showH.value = false;
    showK.value = false;
    showS.value = true;
    logo.value = false;
}

</script>

<template>
    <div class="flex justify-center items-center h-[100vh] bg-zinc-900 ">
        <div class="bg-black text-white p-7 rounded-3xl ">
            <div class="m-1 ">
                <button @click="h"
                    class="px-3 py-1 mx-2 border border-white transition hover:bg-white hover:text-black">H 💕</button>
                <button @click="k"
                    class="px-3 py-1 mx-2 border border-white  transition hover:bg-white hover:text-black">K
                    (●'◡'●)</button>
                <button @click="s"
                    class="px-3 py-1  mx-2 border border-white  transition hover:bg-white hover:text-black">S
                    ❤️</button>
            </div>
            <div>
                <img src="https://www.stereotype.co.jp/images/works_content/2131/2131_1_s1400.jpg" alt=""
                    class="size-40 mt-12 mx-auto object-cover" v-if="logo">
                <img src="https://i.pinimg.com/originals/fc/89/02/fc890248c339ba50190a3a504b879d40.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showH">

                <img src="https://i.pinimg.com/originals/aa/3c/9c/aa3c9cee9867f86327b88b3af6540a61.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showK">


                <img src="https://i.pinimg.com/736x/e6/69/60/e6696050a56af48ae3527fe2298a14ee.jpg" alt=""
                    class="size-40 mt-12 mx-auto" v-if="showS">
            </div>
            <div class=" flex flex-col justify-center items-center pb-3">
                <p class="mt-4 flex">Name: {{ name }}</p>
                <p class="flex">Band: {{ band }}</p>
            </div>
        </div>
    </div>

</template>

