<template>
    <div class="bg-secondary/50 rounded-2xl p-5 mb-6">
        <div class="space-y-3 mb-4">
            <div v-for="item in orderItems" :key="item.id" class="flex items-start justify-between">
                <div class="flex items-start gap-2">
                    <div class="w-1.5 h-1.5 rounded-full bg-primary mt-2 shrink-0"></div>
                    <div>
                        <div class="text-sm font-medium text-gray-900">{{ item.quantity }}x {{ item.name }}</div>
                        <div class="text-xs text-gray-600">{{ item.variant }}</div>
                    </div>
                </div>
                <div class="text-sm font-bold text-gray-900">RM {{ item.price.toFixed(2) }}</div>
            </div>
        </div>

        <div class="flex justify-between items-center text-sm py-3 border-t border-border">
            <span class="text-gray-600">Penghantaran</span>
            <span class="font-medium text-gray-900">RM {{ shipping.toFixed(2) }}</span>
        </div>

        <div class="flex justify-between items-center pt-4 border-t-2 border-primary/20">
            <span class="text-base font-bold text-gray-900">Jumlah Keseluruhan</span>
            <span class="text-2xl font-bold text-primary">RM {{ total.toFixed(2) }}</span>
        </div>
    </div>
</template>

<script setup>
    const orderItems = ref([
        {
            id: 1,
            name: "Kerepek Ubi Pedas",
            variant: "(500g)",
            quantity: 1,
            price: 15.0,
        },
        {
            id: 2,
            name: "Kuah Rojak Madu",
            variant: "(Kecil)",
            quantity: 1,
            price: 20.0,
        },
    ]);

    const shipping = ref(5.0);

    const total = computed(() => {
        const itemsTotal = orderItems.value.reduce((sum, item) => sum + item.price, 0);
        return itemsTotal + shipping.value;
    });
</script>
