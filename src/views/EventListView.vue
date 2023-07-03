<script setup lang="ts">
// import TheWelcome from '../components/TheWelcome.vue'
import EventCard from '@/components/EventCard.vue';
import type { EventItem } from '@/type';
import axios from 'axios'
import { ref } from 'vue'
const events: ref<Array<EventItem>> = ref([])

axios.get<EventItem[]>('http://localhost:3004/events').then((res) => {
  events.value = res.data
})
</script>

<template>
  <main class="events">
    <!-- <TheWelcome /> -->
    <EventCard v-for="event in events" :key="event.id" :event="event"></EventCard>
  </main>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
