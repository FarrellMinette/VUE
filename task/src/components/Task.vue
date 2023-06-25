<template>
    <div class="task-item" v-bind:class="{'is-complete':task.completed}">
    <input type="checkbox" v-on:change="markComplete">
        {{task.title}}
        <button @click="$emit('del-task',task.id)">Delete Task</button>
    </div>    
</template>

<script>
export default {
    name: "TaskMan",
    props: ["task"],
    data() {
        return {
            localTask: this.task,
        }
    },
    methods: {
        markComplete() {
            this.localTask.completed = !this.localTask.completed;
        }
    }
}
</script>

<style scoped>
    .task-item {
        background: #8b8b86;
        padding: 4px;
        border-bottom: 1px #ccc dotted;
    }
    .is-complete {
        text-decoration: line-through;
    }
</style>