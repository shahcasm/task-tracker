<template>
    <div :key="task.id" v-for="task in tasks">
        <Task 
        @toggle-reminder="this.$emit('toggle-reminder', task.id)"
        @delete-task="this.$emit('delete-task', task.id)" v-bind:task="task"/>
    </div>
</template>

<script>

import Task from './Task'

export default{
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        Task,
    },
    emits: ['delete-task', 'toggle-reminder'],
}
</script>