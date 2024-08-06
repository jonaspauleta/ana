<template>
    <UContainer class="min-h-screen flex items-center">
        <UCard class="flex-1" :ui="{ background: 'bg-gray-50 dark:bg-gray-800/50', ring: 'ring-1 ring-gray-300 dark:ring-gray-700', divide: 'divide-y divide-gray-300 dark:divide-gray-700', header: { base: 'font-bold' } }">
            <template #header>
                <p class="text-4xl text-center font-bold">Ana 💜</p>
            </template>

            <div class="text-center flex flex-col space-y-4">
                <Coundown :time="time[0]" v-slot="{ days, hours, minutes, seconds }">
                    Time remaining to be on holidays 🏖️ and say goodbye to 🐬: <br>{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.
                </Coundown>

                <Coundown :time="time[1]" v-slot="{ days, hours, minutes, seconds }">
                    Time remaining to be working on Pearlmaster 💎: <br>{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.
                </Coundown>

                <Coundown :time="time[2]" v-slot="{ days, hours, minutes, seconds }">
                    Time remaining to go to the observatory 🌌: <br>{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.
                </Coundown>

                <Coundown :time="time[3]" v-slot="{ days, hours, minutes, seconds }">
                    Time remaining for Ana's 25yo 💜🐓: <br>{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.
                </Coundown>
            </div>
        </UCard>
    </UContainer>
</template>

<script setup>
import { ref } from 'vue';

const time = ref([
    new Date('2024-08-14T18:00:00') - new Date,
    new Date('2024-09-02T09:00:00') - new Date,
    new Date('2024-08-09T21:15:00') - new Date,
    new Date('2025-02-12T21:15:00') - new Date,
]);
</script>

<style>
body {
  @apply antialiased font-sans text-gray-700 dark:text-gray-200 bg-white dark:bg-gray-900;
}
</style>
