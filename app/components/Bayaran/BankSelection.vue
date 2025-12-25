<template>
    <div class="mb-6">
        <h3 class="text-sm font-bold text-gray-900 mb-4">Pilih Bank Pilihan</h3>

        <div class="grid grid-cols-2 sm:grid-cols-3 gap-3">
            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'maybank' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="maybank" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">Maybank2u</div>
                    <div class="text-xs text-gray-600">Perbankan Dalam Talian</div>
                </div>
                <div v-if="selectedBank === 'maybank'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>

            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'cimb' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="cimb" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">CIMB Clicks</div>
                    <div class="text-xs text-gray-600">Perbankan Dalam Talian</div>
                </div>
                <div v-if="selectedBank === 'cimb'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>

            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'public' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="public" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">Public Bank</div>
                    <div class="text-xs text-gray-600">PBe</div>
                </div>
                <div v-if="selectedBank === 'public'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>

            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'rhb' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="rhb" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">RHB Now</div>
                    <div class="text-xs text-gray-600">Perbankan Dalam Talian</div>
                </div>
                <div v-if="selectedBank === 'rhb'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>

            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'ambank' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="ambank" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">AmOnline</div>
                    <div class="text-xs text-gray-600">AmBank</div>
                </div>
                <div v-if="selectedBank === 'ambank'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>

            <label
                :class="[
                    'relative flex flex-col items-center p-4 rounded-xl border-2 cursor-pointer transition-all duration-200',
                    selectedBank === 'fpx' ? 'border-primary bg-primary/5 shadow-md' : 'border-border bg-white hover:border-primary/50 hover:shadow-sm',
                ]"
            >
                <input v-model="selectedBank" type="radio" name="bank" value="fpx" class="sr-only" />
                <Icon name="mdi:bank" class="text-2xl text-primary mb-2" />
                <div class="text-center">
                    <div class="text-sm font-bold text-gray-900">FPX</div>
                    <div class="text-xs text-gray-600">Bank Lain</div>
                </div>
                <div v-if="selectedBank === 'fpx'" class="absolute top-2 right-2">
                    <Icon name="mdi:check-circle" class="text-lg text-primary" />
                </div>
            </label>
        </div>
    </div>
</template>

<script setup>
    const selectedBank = ref("maybank");
</script>
