<template>
    <div class="max-w-2xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <div class="bg-white rounded-3xl shadow-xl overflow-hidden">
            <div class="bg-secondary px-6 py-4 flex items-center gap-2">
                <Icon name="mdi:shield-check" class="text-green-600 text-xl" />
                <span class="text-sm font-semibold text-gray-700 uppercase tracking-wide">Pembayaran Selamat</span>
            </div>

            <div class="p-6 sm:p-8">
                <div class="mb-8">
                    <h1 class="text-2xl sm:text-3xl font-bold text-gray-900 mb-2">Selesaikan Pembelian Anda</h1>
                    <p class="text-sm text-gray-600">Anda membuat pembayaran kepada <span class="font-semibold text-gray-900">ABC Kerepek Enterprise</span></p>
                </div>
                <BayaranOrderItems />
                <BayaranBankSelection />
                <BayaranEmailInput />
                <BayaranPaymentButton />
                <div class="text-center mt-6">
                    <NuxtLink to="/pembayaran" class="text-sm text-gray-600 hover:text-primary transition-colors underline">Batal dan kembali ke kedai</NuxtLink>
                </div>

                <div class="flex items-center justify-center gap-6 mt-8 pt-6 border-t border-border">
                    <div class="text-xs text-gray-500 font-medium">FPX</div>
                    <div class="text-xs text-gray-500 font-medium">MEPS</div>
                    <div class="text-xs text-gray-500 font-medium">SSL SECURE</div>
                </div>
            </div>
        </div>
    </div>
</template>
