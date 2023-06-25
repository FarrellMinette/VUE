<template>
<div>
    <div v-bind:key="task.id" v-for="task in tasks">
        <TaskMan v-bind:task="task" v-on:del-task="$emit('del-task',task.id)"/>
    </div>
</div>
</template>

<script>
import TaskMan from './Task';

export default {
    components: {
        TaskMan
    },
    name: "TaskManager",
    props: ["tasks"]
}
</script>

<style scope>
</style>
