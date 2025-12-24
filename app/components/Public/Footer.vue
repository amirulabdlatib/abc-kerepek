<template>
    <footer class="bg-white border-t border-border">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
            <!-- Main Footer Content -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-8">
                <!-- Company Info -->
                <div class="space-y-4">
                    <div class="flex items-center gap-2">
                        <NuxtImg src="/images/ara-kerepek-icon.png" alt="Ara Kerepek Logo" class="w-8 h-8 object-contain" />
                        <span class="font-bold text-primary text-lg">Ara Kerepek</span>
                    </div>
                    <p class="text-sm text-gray-600">Penyedia kerepek dan kuah rojak premium buatan Malaysia. Rasa asli warisan nenek moyang disajikan dengan kepakaran tinggi.</p>
                    <!-- Social Media Links -->
                    <div class="flex gap-3">
                        <a href="#" class="w-9 h-9 bg-white rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors duration-200">
                            <Icon name="mdi:facebook" class="text-xl" />
                        </a>
                        <a href="#" class="w-9 h-9 bg-white rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors duration-200">
                            <Icon name="mdi:instagram" class="text-xl" />
                        </a>
                        <a href="#" class="w-9 h-9 bg-white rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors duration-200">
                            <Icon name="mdi:whatsapp" class="text-xl" />
                        </a>
                    </div>
                </div>

                <!-- Quick Links - Pautan Pantas -->
                <div>
                    <h3 class="font-bold text-gray-900 mb-4">Pautan Pantas</h3>
                    <ul class="space-y-2">
                        <li v-for="link in quickLinks" :key="link.name">
                            <NuxtLink :to="link.path" class="text-sm text-gray-600 hover:text-primary transition-colors duration-200">
                                {{ link.name }}
                            </NuxtLink>
                        </li>
                    </ul>
                </div>

                <!-- Hubungi Kami -->
                <div>
                    <h3 class="font-bold text-gray-900 mb-4">Hubungi Kami</h3>
                    <ul class="space-y-3">
                        <li class="flex items-start gap-2 text-sm text-gray-600">
                            <Icon name="mdi:phone" class="text-primary mt-0.5 shrink-0" />
                            <a href="tel:01X-XXXXXXX" class="hover:text-primary transition-colors duration-200">01X-XXXXXXX</a>
                        </li>
                        <li class="flex items-start gap-2 text-sm text-gray-600">
                            <Icon name="mdi:email" class="text-primary mt-0.5 shrink-0" />
                            <a href="mailto:hello@arakerepek.my" class="hover:text-primary transition-colors duration-200">hello@arakerepek.my</a>
                        </li>
                        <li class="flex items-start gap-2 text-sm text-gray-600">
                            <Icon name="mdi:map-marker" class="text-primary mt-0.5 shrink-0" />
                            <span>Kuala Lumpur, Malaysia</span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Bottom Bar -->
            <div class="border-t border-border pt-6">
                <div class="flex flex-col md:flex-row justify-between items-center gap-4">
                    <p class="text-sm text-gray-600 text-center md:text-left">
                        © {{ currentYear }} Ara Kerepek Enterprise.
                        <br class="md:hidden" />
                        No. Pendaftaran: 202403124880
                    </p>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>
    const currentYear = new Date().getFullYear();

    const quickLinks = [
        { name: "Utama", path: "/" },
        { name: "Produk", path: "/produk" },
    ];
</script>
