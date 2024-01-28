<template>
    <div class="a-page home">
        <button @click="handleSubmit">Submit</button>
    </div>
</template>
<script setup lang="ts">
defineOptions({
    name: 'HomeView',
    title: '首页'
})
import { ref } from 'vue'
import { useSocketStore } from '@/stores'
const { play } = useSocketStore()
const form = ref({
    name: '',
    post: '',
    isRead: false
})
const handleSubmit = () => {
    console.log(form.value)
    play(form.value)
}
</script>
<style lang="scss">
@import './index.scss';
</style>
