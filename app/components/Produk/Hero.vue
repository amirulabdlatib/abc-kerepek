<template>
    <section class="bg-primary py-12 lg:py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center text-white space-y-4">
                <!-- Title -->
                <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold">Produk Kami</h1>

                <!-- Subtitle -->
                <p class="text-sm sm:text-base text-white/90 max-w-2xl mx-auto">Rasa Asli Tradisi Kami — Rangup, Pedas, Memikat!</p>

                <!-- Search Bar -->
                <div class="max-w-2xl mx-auto pt-4">
                    <div class="relative">
                        <Icon name="mdi:magnify" class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400 text-xl" />
                        <input v-model="searchQuery" type="text" placeholder="Cari kerepek kegemaran anda..." class="w-full pl-12 pr-32 py-3 rounded-full text-sm focus:outline-none focus:ring-2 focus:ring-primary-light" />
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
