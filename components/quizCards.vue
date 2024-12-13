<script setup>
const data = await useQuizs();
provide('data', data);
</script>

<template>
    <div class="flex flex-col gap-7 max-w-xl mx-auto">
        <div v-for="quizz in data.quizzs" :key="quizz._path" class="flex flex-col gap-2 p-4 bg-white shadow-md rounded-lg">
            <h3 class="text-2xl font-semibold">{{ quizz.title }}</h3>
            <p class="text-sm text-gray-600">Nombre de questions : {{ quizz.questions.length }}</p>
            <NuxtLink 
                :to="`/${quizz._path.split('/').pop()}`"
                class="bg-purple-500 hover:bg-purple-700 text-white p-2 rounded-md text-center transition duration-300"
            >
                Commencer le quizz
            </NuxtLink>
        </div>
    </div>
</template>