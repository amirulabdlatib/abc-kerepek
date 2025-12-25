<template>
    <div class="mb-6">
        <label for="email" class="block text-sm font-bold text-gray-900 mb-3">E-mel untuk Resit</label>
        <div class="relative">
            <Icon name="mdi:email-outline" class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400 text-lg" />
            <input
                id="email"
                v-model="email"
                type="email"
                placeholder="customer@email.com"
                class="w-full pl-11 pr-4 py-3 rounded-lg border border-border bg-white text-sm text-gray-900 placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors"
            />
        </div>
        <div class="flex items-start gap-2 mt-2">
            <Icon name="mdi:information-outline" class="text-gray-500 text-sm mt-0.5 shrink-0" />
            <p class="text-xs text-gray-600">Kami akan menghantar pengesahan pembayaran ke e-mel ini.</p>
        </div>
    </div>
</template>

<script setup>
    const email = ref("");
</script>
