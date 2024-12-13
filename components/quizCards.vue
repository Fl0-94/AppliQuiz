<script setup>
const data = await useQuizs();
provide('data', data);
</script>

<template>
    <div class="flex flex-col gap-7 max-w-xl mx-auto mt-10">
        <div v-for="quizz in data.quizzs" :key="quizz._path" class="flex flex-col gap-4 p-6 bg-white shadow-lg rounded-lg">
            <h3 class="text-2xl font-semibold">{{ quizz.title }}</h3>
            <p class="text-sm text-gray-600">Nombre de questions : {{ quizz.questions.length }}</p>
            <NuxtLink 
                :to="`/${quizz._path.split('/').pop()}`"
                class="bg-purple-500 hover:bg-purple-700 text-white py-2 px-4 rounded-md text-center transition duration-300"
            >
                Commencer le quizz
            </NuxtLink>
        </div>
    </div>
</template>