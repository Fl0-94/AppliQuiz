<script setup>
    const quizz = inject('quizz')
</script>

<template>
    <div class="max-w-sm sm:max-w-xl mx-auto flex flex-col gap-6">
        <div class="flex justify-between items-center">
            <h1 class="text-2xl">Résultat</h1>
            <ResultatScore />
        </div>
     
        <ul class="flex flex-col gap-4">
            <li 
            v-for="(question, index) in quizz.data.questions" 
            :key="index"
            class="border border-gray-300 p-4 rounded"
            >
                {{ question.title }} {{ question.correctAnswer }}
            </li>
        </ul>

        <div class="flex justify-between">
            <Button @click="quizz.reset()">Retente ta chance !</Button>
            <NuxtLink to="/">
                <Button>Essaye d'autres quizz</Button>
            </NuxtLink>
        </div>
    </div>
</template>