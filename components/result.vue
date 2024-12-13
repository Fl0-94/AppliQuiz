<script setup>
    const quizz = inject('quizz')
</script>

<template>
    <div class="max-w-sm sm:max-w-xl mx-auto flex flex-col gap-8 mt-10 p-6 bg-white shadow-lg rounded-lg">
        <div class="flex justify-between items-center mb-6">
            <h1 class="text-3xl font-bold">Résultat</h1>
            <ResultatScore />
        </div>
     
        <ul class="flex flex-col gap-4">
            <li 
                v-for="(question, index) in quizz.data.questions" 
                :key="index"
                class="border border-gray-300 p-4 rounded-lg bg-gray-50"
            >
                <p class="font-semibold">{{ question.title }}</p>
                <p class="text-green-600">{{ question.correctAnswer }}</p>
            </li>
        </ul>

        <div class="flex justify-between mt-6">
            <Button @click="quizz.reset()" class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded-md transition duration-300">Retente ta chance !</Button>
            <NuxtLink to="/">
                <Button class="bg-purple-500 hover:bg-purple-700 text-white py-2 px-4 rounded-md transition duration-300">Essaye d'autres quizz</Button>
            </NuxtLink>
        </div>
    </div>
</template>