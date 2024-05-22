<script setup>
import { ref } from "vue";

const ROLES = ["Administrador", "Usuario", "Cliente", "Pepe"];
const COLORS = ["Azul", "amarillo", "Rojo"];
const MIMIS = ref([
    { name: "mimi", color: "red" },
    { name: "meme", color: "blue" },
    { name: "momo", color: "green" },
    { name: "mumu", color: "yellow" }
]);

const firstMimiName = MIMIS.value[0].name;
const firstMimiColor = MIMIS.value[0].color;

let lista = ref(false);
let actual = ref("");

let primero = ref(false);
let segundo = ref(false);
let tercero = ref(false);
let cuarto = ref(false);
let defecto = ref(true);

let blue = ref(false);
let box1 = ref(true);

let yellow = ref(false);
let box2 = ref(true);

let red = ref(false);
let box3 = ref(true);

function changeColor(index){
   if(index == 0){
    blue.value = true;
    box1.value = false;
   }
    if (index == 1) {
        yellow.value = true;
        box2.value = false;
    }
    if (index == 2) {
        red.value = true;
        box3.value = false;
    }
}

function mimito(index){
    
    if(index == 0){
        console.log("mimi te amo");
        MIMIS[0] = "mimito";
    }
}

function escogerRol(){
    lista.value = true;
}

function rolsito(index){
    actual.value = ROLES[index];
    lista.value = false;

    if(index ==0){
        defecto.value = false;
        primero.value = true;
        segundo.value = false;
        tercero.value = false;
        cuarto.value = false;
    }

    if (index == 1) {
        defecto.value = false;
        primero.value = false;
        segundo.value = true;
        tercero.value = false;
        cuarto.value = false;
    }

    if (index == 2) {
        defecto.value = false;
        primero.value = false;
        segundo.value = false;
        tercero.value = true;
        cuarto.value = false;
    }

    if (index == 3) {
        defecto.value = false;
        primero.value = false;
        segundo.value = false;
        tercero.value = false;
        cuarto.value = true;
    }

}


</script>

<template>
    <div class="h-[100vh] bg-zinc-200 p-6">
        <div class="flex justify-evenly">
            <p class="mb-4 size-20">Rol actual:
            <p class="font-bold">{{ actual }}</p>
            </p>
            <div class="flex justify-between bg-slate-200 w-[900px] items-center p-3 rounded-2xl shadow-md"
                v-if="defecto">
                <p class="mx-3"></p>
                <p class="mx-3"></p>
                <p class="mx-3">{{ actual }}</p> <img
                    src="https://i.pinimg.com/564x/e8/d7/d0/e8d7d05f392d9c2cf0285ce928fb9f4a.jpg" alt=""
                    class="size-14 rounded-full">
            </div>
            <div class="flex justify-between bg-blue-200 w-[900px] items-center p-3 rounded-2xl  shadow-md"
                v-if="primero">
                <p class="mx-3">hola </p>
                <p class="mx-3">bienvenido</p>
                <p class="mx-3">{{actual}}</p> <img
                    src="https://i.pinimg.com/564x/27/28/22/2728222787ff3b2afb93d4cea84f42dd.jpg" alt=""
                    class="size-14 rounded-full">
            </div>

            <div class="flex justify-between bg-red-200 w-[900px] items-center p-3 rounded-2xl shadow-md"
                v-if="segundo">
                <p class="mx-3">viva</p>
                <p class="mx-3">Reimu</p>
                <p class="mx-3">{{ actual }}</p> <img
                    src="https://i.pinimg.com/564x/58/17/d7/5817d7a42fdd9c4e49b41d4bc3e56f1f.jpg" alt=""
                    class="size-14 rounded-full">
            </div>

            <div class="flex justify-between bg-orange-200 w-[900px] items-center p-3 rounded-2xl shadow-md"
                v-if="tercero">
                <p class="mx-3">hola</p>
                <p class="mx-3">bienvenido</p>
                <p class="mx-3">{{ actual }}</p> <img
                    src="https://i.pinimg.com/564x/42/50/a3/4250a3e1d1cb90016ca211adbc993b13.jpg" alt=""
                    class="size-14 rounded-full">
            </div>

            <div class="flex justify-between bg-green-200 w-[900px] items-center p-3 rounded-2xl shadow-md"
                v-if="cuarto">
                <p class="mx-3">hola 💕</p>
                <p class="mx-3">bienvenido ❤️</p>
                <p class="mx-3">{{ actual }}</p> <img
                    src="https://i.pinimg.com/564x/1a/fd/2a/1afd2acaffa0abffe9b622ce515d8650.jpg" alt=""
                    class="size-14 rounded-full">
            </div>
        </div>


        <div class="flex absolute">
            <ul class="my-12 ml-14 relative">
                <button @click="escogerRol()"
                    class="border border-black p-2 rounded-xl hover:bg-zinc-500 hover:text-white transition ">Seleccionar
                    rol</button>
                <li class="bg-zinc-300 p-2 border border-white rounded-xl hover:cursor-pointer" @click="rolsito(index)"
                    v-for="(text, index) in ROLES" :key="index" v-if="lista">

                    {{ text }}
                </li>
            </ul>

        </div>

        <div class="flex mt-32 gap-4">
            <div class="size-20 border border-black" v-if="box1"></div>
            <div class="size-20 border border-black bg-blue-700" v-if="blue"></div>

            <div class="size-20 border border-black" v-if="box2"></div>
            <div class="size-20 border border-black bg-yellow-400" v-if="yellow"></div>

            <div class="size-20 border border-black" v-if="box3"></div>
            <div class="size-20 border border-black bg-red-600" v-if="red"></div>
        </div>
        <div class="flex items-start">

            <ul class="flex">
                <li class="border border-black p-2 rounded-2xl mt-3 hover:cursor-pointer"
                    v-for="(text, index) in COLORS" :key="index" @click="changeColor(index)">
                    {{ text }}
                </li>

            </ul>

        </div>

      


    </div>
</template>