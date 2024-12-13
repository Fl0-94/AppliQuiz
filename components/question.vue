<script setup>
    const quizz = inject('quizz')
</script>

<template>
    <div class="max-w-sm sm:max-w-xl mx-auto flex flex-col gap-8 mt-10 p-6 bg-white shadow-lg rounded-lg">
        <div class="flex justify-between items-center">
            <p class="text-lg font-semibold">{{ quizz.data.questions[quizz.currentQuestionIndex.value].title }}</p>
            <p class="text-sm text-gray-500">{{ quizz.currentQuestionIndex.value + 1 }} / {{ quizz.data.questions.length }}</p>
        </div>
       
        <form @submit.prevent="quizz.next()">
            <div class="flex gap-4 pb-6 flex-col sm:flex-row">
                <AnswerCards />
            </div>
           
            <Button type="submit" class="w-full bg-purple-500 hover:bg-purple-700 text-white py-2 px-4 rounded-md transition duration-300">Next</Button>
        </form>
    </div>
</template>