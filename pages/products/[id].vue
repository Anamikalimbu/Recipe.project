<template>
    <div class="bg" >
        <div v-if="pending" class="loading">
<img src="~assets/images/loading.gif"  alt="">
        </div>
        <div class="grid lg:grid-cols-4 md:grid-cols-2 sm:grid-cols-1" v-else>
            <div class="box col-span-2">
            <h1 class="lg:text-4xl m pb-2 align-text-top"> {{ meal.meals[0].strMeal }}</h1>
        <img :src="meal.meals[0].strMealThumb" alt="">
        </div>
            <div class="col-span-2">
                <h1 class="text-4xl text-blue-600 pb-2  ">Ingredients  </h1>

                    <div>
                        <p>{{ meal.meals[0].strIngredient1 }} :
                        {{ meal.meals[0].strMeasure1 }}</p>
                    <p>{{ meal.meals[0].strIngredient2 }} :
                        {{ meal.meals[0].strMeasure2 }}</p>
                    <p>{{ meal.meals[0].strIngredient3 }} :
                        {{ meal.meals[0].strMeasure3 }}</p>
                    <p>{{ meal.meals[0].strIngredient4 }} :
                        {{ meal.meals[0].strMeasure4 }}</p>
                    <p>{{ meal.meals[0].strIngredient5 }} :
                        {{ meal.meals[0].strMeasure5 }}</p>
                    <p>{{ meal.meals[0].strIngredient6 }} :
                        {{ meal.meals[0].strMeasure6 }}</p>
                    <p>{{ meal.meals[0].strIngredient7 }} :
                        {{ meal.meals[0].strMeasure7 }}</p>
                    <p>{{ meal.meals[0].strIngredient8 }} :
                        {{ meal.meals[0].strMeasure8 }}</p>
                    <p>{{ meal.meals[0].strIngredient9 }} :
                        {{ meal.meals[0].strMeasure9 }}</p>
                    <p>{{ meal.meals[0].strIngredient10 }} :
                        {{ meal.meals[0].strMeasure10 }}</p>
                    <p>{{ meal.meals[0].strIngredient11 }} :
                    {{ meal.meals[0].strMeasure11 }}</p>
                    <p>{{ meal.meals[0].strIngredient12 }} :
                    {{ meal.meals[0].strMeasure12 }}</p>
                    <p>{{ meal.meals[0].strIngredient13 }} :
                    {{ meal.meals[0].strMeasure13 }}</p>
                    <p>{{ meal.meals[0].strIngredient14 }} :
                    {{ meal.meals[0].strMeasure14 }}</p>
                    <p>{{ meal.meals[0].strIngredient15 }} :
                    {{ meal.meals[0].strMeasure15 }}</p>
                    <p>{{ meal.meals[0].strIngredient16 }} :
                    {{ meal.meals[0].strMeasure16 }}</p>
                    <p>{{ meal.meals[0].strIngredient17 }} :
                    {{ meal.meals[0].strMeasure17 }}</p>
                    <p>{{ meal.meals[0].strIngredient18 }} :
                    {{ meal.meals[0].strMeasure18 }}</p>
                    <p>{{ meal.meals[0].strIngredient19 }} :
                    {{ meal.meals[0].strMeasure19 }}</p>
                    <p>{{ meal.meals[0].strIngredient20 }} :
                    {{ meal.meals[0].strMeasure20 }}</p>
                    </div>
        
            </div>
        </div>

    <div class="bg container m-auto">
        <h1 class="strMeal text-4xl"> Name : {{ meal.meals[0].strMeal }}</h1>
        <h2 class="strCategory font-extrabold text-3xl">Category : {{ meal.meals[0].strCategory }}</h2>
        <h2 class="text-3xl text-start ">Instruction : </h2>
        <p class=" font-serif">{{ meal.meals[0].strInstructions }}</p>
        <h1 class="text-3xl "> Watch On Youtube</h1>
        <a :href="meal.meals[0].strYoutube" target="_blank"> <i class="fa-brands fa-youtube text-5xl text-red-500"></i>
 {{ meal.meals[0].StrMeal }}</a>
    </div>
    </div>
</template>

<script setup>
const route = useRoute();
const url =ref(`https://themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`)
const { data: meal , pending  } =  useFetch(url, { refetch: true })


</script>


<style  scoped>
.bg {
    background: #302414;
    text-align: center;
    color: #fff;
}
.loading{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
}

.strMeal {
    text-align: center;
    justify-content: center;
    align-items: center;
    color: #fff;
}

.box {
    margin-top: 40px;
    margin-left: 40px;
    height: 400px;
    width: 400px;
    overflow: hidden;
}

.box-img {
    margin-top: 40px;
    margin-left: 40px;
    height: 400px;
    width: 400px;
    object-fit: cover;
}

.strCategory {
    text-align: center;
    justify-content: center;
    align-items: center;
    color: #fff;
}</style>