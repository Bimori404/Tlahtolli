<template>
    <div class="flex items-center gap-4 mb-6">
        <div class="relative">
            <div class="w-20 h-20 rounded-full overflow-hidden bg-gray-700">
                <!-- <img :src="user.profileImage" :alt="`Foto de perfil de ${user.name}`" class="w-full h-full object-cover" /> -->
            </div>
            <Badge
                class="absolute -bottom-1 -right-1 bg-[#58CC02] text-white text-xs font-bold rounded-full w-6 h-6 flex items-center justify-center">
                {{ user.level }}
            </Badge>
        </div>
        <div class="flex-1">
            <h2 class="text-xl font-bold">{{ user.name }}</h2>
            <p class="text-gray-400 text-sm">@{{ user.username }}</p>
            <div class="mt-1">
                <div class="flex justify-between text-xs text-gray-400 mb-1">
                    <span>Nivel {{ user.level }}</span>
                    <span>
                        {{ user.xp }}/{{ user.xpToNextLevel }} XP
                    </span>
                </div>
                <ProgressBar :current="user.xp" :total="user.xpToNextLevel" class="h-1.5 bg-gray-700" />
            </div>
        </div>
    </div>
</template>

<script setup>
import Badge from './Badge.vue';
import ProgressBar from './ProgressBar.vue';

defineProps({
    user: {
        type: Object,
        required: true
    }
});
</script>