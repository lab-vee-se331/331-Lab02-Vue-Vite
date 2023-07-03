<template>
    <div class="event-class">
        <div class="event-card">

            <h4>category : {{ event.category }}</h4>
            <h4>by : {{ event.organizer }}</h4>
        </div>
    </div>
</template>

<script setup lang="ts">
import type { EventItem } from '@/type';
import type { PropType } from 'vue';
const props = defineProps({
    event: {
        type: Object as PropType<EventItem>
        , require: true
    }
})
</script>
<!-- import { ref } from 'vue'
import { type EventItem } from '@/type';
const event = ref<EventItem>({
    id: 5928101,
    category: 'animal welfare',
    title: 'Cat Adoption Day',
    description: 'Find your new feline friend at this event',
    location: 'Meow Town',
    date: 'January 28, 2002',
    time: '12:00',
    petsAllowed: true,
    organizer: "Kat Laydee"
}) -->

<style scoped>
.event-card {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
}

.event-card:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgb(0, 0, 0, 0.2);
}

* {
    text-align: right;
}
</style>