<script setup lang="ts">
import { defineProps } from 'vue'
import type { StudentItem } from '@/type';

const props = defineProps({
    student: {
        type: Object as PropType<StudentItem>,
        required: true,
    }
});
</script>

<template>
    <div class="event-class">
        <div class="event-card">
            <span>Name: {{ student.name }}, Surname: {{ student.surname }}</span>
            <h4>GPA: {{ student.gpa }}</h4>
        </div>
    </div>
</template>

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
</style>