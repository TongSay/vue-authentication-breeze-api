<template>
    <div v-if="authStore.user">
        <h1>{{ authStore.user?.name }}</h1>
        <p>{{ authStore.user?.email }}</p>
    </div>
    <div v-else>
    <p>Go to Login</p>
    </div>
</template>

<script setup>
 import { onMounted } from 'vue';
 import { useAuthStore } from '../stores/auth';

 const authStore = useAuthStore();
 
 onMounted( async () => {
    await authStore.getUser();
   
 })

 
</script>
