<template>
    <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
        <!-- Filter Tabs -->
        <div class="flex flex-wrap gap-3 mb-10 justify-center">
            <button
                v-for="category in categories"
                :key="category.id"
                @click="selectedCategory = category.id"
                :class="['px-6 py-2 rounded-full text-sm font-medium transition-all duration-200', selectedCategory === category.id ? 'bg-primary text-white' : 'bg-white text-gray-700 border border-primary hover:bg-secondary-accent']">
                {{ category.name }}
            </button>
        </div>

        <!-- Products Grid -->
        <div v-if="filteredProducts.length > 0" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Product Card -->
            <div v-for="product in filteredProducts" :key="product.id" class="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-xl transition-all duration-300 group">
                <!-- Product Image -->
                <div class="relative overflow-hidden bg-gray-900 aspect-square">
                    <!-- Badge -->
                    <div v-if="product.badge" class="absolute top-3 left-3 z-10">
                        <span :class="['text-xs font-bold px-3 py-1 rounded-full', product.badge === 'LARIS' ? 'bg-orange-500 text-white' : 'bg-yellow-500 text-gray-900']">
                            {{ product.badge }}
                        </span>
                    </div>

                    <NuxtImg :src="product.image" :alt="product.name" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500" />
                </div>

                <!-- Product Info -->
                <div class="p-5">
                    <h3 class="font-bold text-lg text-gray-900 mb-2">{{ product.name }}</h3>
                    <p class="text-sm text-gray-600 mb-4 line-clamp-2">{{ product.description }}</p>

                    <!-- Price & Cart -->
                    <div class="flex items-center justify-between">
                        <div class="text-primary font-bold text-xl">RM {{ product.price }}</div>
                        <button class="w-10 h-10 bg-primary text-white rounded-full flex items-center justify-center hover:bg-primary-dark transition-colors duration-200 group-hover:scale-110">
                            <Icon name="mdi:cart-plus" class="text-xl" />
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Empty State -->
        <div v-else class="text-center py-16">
            <div class="max-w-md mx-auto">
                <!-- Empty Icon -->
                <div class="w-24 h-24 bg-secondary rounded-full flex items-center justify-center mx-auto mb-6">
                    <Icon name="mdi:package-variant" class="text-5xl text-primary/50" />
                </div>

                <!-- Empty Text -->
                <h3 class="text-xl font-bold text-gray-900 mb-2">Tiada Produk Dijumpai</h3>
                <p class="text-sm text-gray-600 mb-6">Maaf, tiada produk dalam kategori ini buat masa ini. Cuba pilih kategori lain.</p>

                <!-- Reset Button -->
                <button @click="selectedCategory = 'all'" class="bg-primary text-white px-6 py-2.5 rounded-full hover:bg-primary-dark transition-colors duration-200 text-sm font-medium inline-flex items-center gap-2">
                    <Icon name="mdi:refresh" class="text-lg" />
                    <span>Lihat Semua Produk</span>
                </button>
            </div>
        </div>

        <!-- Pagination -->
        <div v-if="filteredProducts.length > 0" class="flex justify-center items-center gap-2 mt-12">
            <button class="w-10 h-10 flex items-center justify-center rounded-full hover:bg-secondary-accent transition-colors duration-200">
                <Icon name="mdi:chevron-left" class="text-xl text-gray-600" />
            </button>

            <button
                v-for="page in [1, 2, 3]"
                :key="page"
                :class="['w-10 h-10 flex items-center justify-center rounded-full text-sm font-medium transition-colors duration-200', page === 1 ? 'bg-primary text-white' : 'bg-white text-gray-700 hover:bg-secondary-accent']">
                {{ page }}
            </button>

            <button class="w-10 h-10 flex items-center justify-center rounded-full hover:bg-secondary-accent transition-colors duration-200">
                <Icon name="mdi:chevron-right" class="text-xl text-gray-600" />
            </button>
        </div>
    </section>
</template>

<script setup>
    const selectedCategory = ref("all");

    const categories = [
        { id: "all", name: "Semua" },
        { id: "kerepek", name: "Aneka Kerepek" },
        { id: "rojak", name: "Kuah Rojak" },
        { id: "kekacang", name: "Kekacang" },
    ];

    const products = [
        {
            id: 1,
            name: "Kerepek Ubi Pedas Basah",
            description: "Kerepek ubi bersalut sambal pedas manis yang rangup dan enak.",
            price: "15.00",
            image: "/images/kerepek-ubi-pedas-basah.png",
            category: "kerepek",
            badge: "LARIS",
        },
        {
            id: 2,
            name: "Kerepek Pisang Salai",
            description: "Hirisan pisang nipis dengan aroma salai yang membangkit selera.",
            price: "18.00",
            image: "/images/kerepek-pisang.png",
            category: "kerepek",
            badge: null,
        },
        {
            id: 3,
            name: "Kuah Rojak Mak Bee",
            description: "Pekat, likat dan penuh rasa. Resepi asli turun temurun.",
            price: "12.00",
            image: "/images/kuah-rojak.png",
            category: "rojak",
            badge: "PREMIUM",
        },
        {
            id: 4,
            name: "Kerepek Bawang",
            description: "Snek ringan yang sesuai untuk minum petang bersama keluarga.",
            price: "10.00",
            image: "/images/kerepek-bawang.png",
            category: "kerepek",
            badge: null,
        },
        {
            id: 5,
            name: "Opak Kari",
            description: "Rasa kari yang 'kaw' dalam setiap gigitan rangup.",
            price: "14.00",
            image: "/images/opak-kari.png",
            category: "kerepek",
            badge: null,
        },
        {
            id: 6,
            name: "Kerepek Ubi Masin",
            description: "Perisa asli masin yang ringkas tetapi menjadi pujaan ramai.",
            price: "13.00",
            image: "/images/kerepek-ubi-masin.png",
            category: "kerepek",
            badge: null,
        },
        {
            id: 7,
            name: "Kerepek Pisang Tanduk",
            description: "Rangup, enak, rasai enak pisang tanduk dengan rasa asin.",
            price: "18.00",
            image: "/images/kerepek-pisang-tanduk.png",
            category: "kerepek",
            badge: "LARIS",
        },
        {
            id: 8,
            name: "Kuah Rojak Botol Besar",
            description: "Saiz besar untuk keluarga. Pekat dan sedap!",
            price: "22.00",
            image: "/images/kuah-rojak.png",
            category: "rojak",
            badge: null,
        },
        {
            id: 9,
            name: "Kerepek Pisang Original",
            description: "Rasa asli pisang yang manis dan rangup.",
            price: "16.00",
            image: "/images/kerepek-pisang.png",
            category: "kerepek",
            badge: null,
        },
    ];

    const filteredProducts = computed(() => {
        if (selectedCategory.value === "all") {
            return products;
        }
        return products.filter((product) => product.category === selectedCategory.value);
    });
</script>
