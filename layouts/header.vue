<template>
    <main>
        <header class="max-w-full bg-gray-800 text-white py-4">
            <div class="max-w-7xl mx-auto flex justify-between items-center px-4">
                <p class="text-xl font-bold">Master Quizz</p>
                <NuxtLink to="/">
                    <Button>Accueil</Button>
                </NuxtLink>
            </div>
        </header>
        <slot />
    </main>
</template>