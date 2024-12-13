<script setup>
import { inject } from 'vue';

const quizz = inject('quizz');
</script>

<template>
    <div v-for="(answer, index) in quizz.data.questions[quizz.currentQuestionIndex.value].answers" 
         :key="index"
         class="flex gap-2 border p-4 rounded-lg w-full bg-gray-100 hover:bg-gray-200 transition duration-300"
    >
        <label class="flex gap-2 w-full cursor-pointer items-center">
            <input 
                type="radio" 
                :value="answer" 
                v-model="quizz.selectedAnswer.value" 
                name="quiz-answer" 
                class="cursor-pointer"
                required
            />
            <span class="text-lg">{{ answer }}</span>
        </label>
    </div>
</template>