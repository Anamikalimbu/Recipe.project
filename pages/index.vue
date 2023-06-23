<template>
    <div class=" bg">
        <h1 class=" text-center text-white text-3xl font-bold py-2 ">Anamikacrew</h1>
        <p class=" text-white font-headings text-center py-3 text-3xl"> This is Recipe Website.I welcome u here. <br> Thank
            You for visiting Our Page. Hope u like and get help to make tasty food.</p>
    </div>
    <hr>


    <div class="py-2 bg ">
        <div class="bg flex justify-center ">
        <label for="" class="text-white text-3xl" >Search Items by name</label>
        <input type="text" v-model="char" class="border py-2 px-2 mx-2 bg-white text-black" />
        <button @click="getUrl(char)" class="py-2 px-5 bg-blue-500 text-white rounded-full ">
            <i class="fa-solid fa-magnifying-glass"></i></button>
            </div>
        <div class="container m-auto grid grid-cols-4 gap-2 ">
            <div v-for="(p, index) in items.meals" :key="index">
                <NuxtLink :to="`/products/${p.idMeal}`">
                    <ProductCard :product="p" />
                </NuxtLink>
            </div>
        </div>
    </div>
    <hr>

    <div class="flex justify-center bg">
        <h1 class="text-white me-10 text-3xl p-2 font-mono">Click here</h1>
        <button class=" bg-yellow-950 me-8 mb-2 text-white">
            <NuxtLink to="/products">Product</NuxtLink>
        </button>
        <button class=" bg-yellow-950 me-8 mb-2 text-white">
            <NuxtLink to="/products/byalphabet">Alphabet</NuxtLink>
        </button>

    </div>
    <hr>
</template>

<script setup>
import { ref } from 'vue';
import {
    SfButton,
    SfIconPerson,
    SfInput,
    SfIconSearch,
} from '@storefront-ui/vue';

const actionItems = [
    {
        label: 'Log in',
        icon: SfIconPerson,
        ariaLabel: 'Log in',
        role: 'login',
    },
];
const char = ref("Arrabiata");
const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?s=Arrabiata");
const { data: items, pending } = await useFetch(url, { refectch: true });
function getUrl(char) {
    url.value = `https://www.themealdb.com/api/json/v1/1/search.php?s=${char}`;
}

</script>

<style  scoped>.bg {
    background-color: #302414;
}</style>