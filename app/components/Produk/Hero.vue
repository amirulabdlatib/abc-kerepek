<template>
    <section class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <div class="bg-primary rounded-2xl py-10 px-6 sm:px-12">
            <div class="text-center text-white space-y-4">
                <h1 class="text-3xl sm:text-xl lg:text-2xl font-bold">Produk Kami</h1>

                <p class="text-sm sm:text-base text-white/90 max-w-2xl mx-auto">Rasa Asli Tradisi Kami — Rangup, Pedas, Memikat!</p>

                <div class="max-w-2xl mx-auto pt-2">
                    <div class="relative">
                        <Icon name="mdi:magnify" class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400 text-xl" />
                        <input v-model="searchQuery" type="text" placeholder="Cari kerepek kegemaran anda..." class="w-full pl-12 pr-32 py-3 rounded-full text-sm text-gray-900 bg-white focus:outline-none focus:ring-2 focus:ring-white/50" />
                        <button class="absolute right-2 top-1/2 -translate-y-1/2 bg-primary hover:bg-primary-dark text-white px-6 py-2 rounded-full text-sm font-medium transition-colors duration-200">Cari</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
    const searchQuery = ref("");
</script>
