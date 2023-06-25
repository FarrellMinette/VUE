<template>
    <div>
        <form @submit="addTask">
            <input type="text" name="title" v-model="title" placeholder="Add Task">
            <input type="submit" value="Add Task">
        </form>
    </div>
</template>

<script>
import {v4} from 'uuid';
export default {
    name: "AddTask",
    data() {
        return {
            title: ''
        }
    },
    methods: 
    {
        addTask(e){
            e.preventDefault();
            const task = {
                id: v4(),
                title: this.title,
                completed: false
            };
            this.$emit('add-task', task)
        }
    }
}
</script>

<style scoped>

</style>