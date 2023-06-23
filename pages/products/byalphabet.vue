<template>
    <div class="bg ">
        <div v-if="pending" class="loading">
<img src="~assets/images/loading.gif" alt="">
        </div>
        <div class="py-2" v-else>
            <label for="" class="text-white">Search Items by Alphabet</label>
        <input type="text" v-model="ch" class="border py-2 px-2 mx-2 bg-white text-black lg:order-3 mt-2 lg:mt-0 pb-2 lg:pb-0 " maxlength="1" />
        <button @click="getUrl(ch)" class="py-2 px-5 bg-blue-500 text-white rounded-full "><i class="fa-solid fa-magnifying-glass"></i></button>
        <div class="container m-auto grid grid-cols-4 gap-2 ">
                <div v-for="(p, index) in items.meals" :key="index">
                <NuxtLink :to="`/products/${p.idMeal}`"><ProductCard :product="p" /></NuxtLink>
            </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const ch = ref("a");
const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?f=a");
const {data: items , pending } = await useFetch(url,{ refectch: true});
function getUrl(ch) {
    url.value=`https://www.themealdb.com/api/json/v1/1/search.php?f=${ch}`;
}
</script>

<style  scoped>
.bg{
    background-color: #302414;

}
.loading{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
}
</style>