<template>
  <NuxtLayout name="header">
    <div class="max-w-2xl mx-auto mt-20 p-8 bg-white shadow-lg rounded-lg text-center">
      <template v-if="error.statusCode === 404">
        <template v-if="error.url && error.url.startsWith('/quizz-')">
          <h1 class="text-4xl font-bold text-red-600">404 - Quiz Introuvable</h1>
          <p class="mt-4 text-lg text-gray-700">Désolé, le quiz que vous cherchez n'existe pas ou a été supprimé.</p>
        </template>
        <template v-else>
          <h1 class="text-4xl font-bold text-red-600">404 - Page Introuvable</h1>
          <p class="mt-4 text-lg text-gray-700">Désolé, la page que vous cherchez n'existe pas.</p>
        </template>
      </template>
      <template v-else>
        <h1 class="text-4xl font-bold text-red-600">Oups !</h1>
        <p class="mt-4 text-lg text-gray-700">
          <strong>{{ error.message }}</strong>
        </p>
        <p class="mt-2 text-lg text-gray-700">Il semble que quelque chose ait mal tourné.</p>
        <p class="mt-2 text-lg text-gray-700">Nous nous excusons pour la gêne occasionnée.</p>
      </template>
      <NuxtLink to="/" class="mt-6 inline-block">
        <Button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded-md transition duration-300">Retour à l'accueil</Button>
      </NuxtLink>
    </div>
  </NuxtLayout>
</template>

<script setup>
defineProps(['error']);
</script>
