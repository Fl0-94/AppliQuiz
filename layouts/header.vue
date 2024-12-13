<template>
    <main>
        <header class="max-w-sm sm:max-w-xl mx-auto text-black py-6 mb-6">
            <div class="max-w-xl flex justify-between mx-auto items-center">
                <p>Master Quizz 	&#x1F44C</p>
                <NuxtLink to="/">
                    <Button> Accueil 	&#x1F3E0</Button>
                </NuxtLink>
            </div>
        </header>
        <slot />
    </main>
</template>