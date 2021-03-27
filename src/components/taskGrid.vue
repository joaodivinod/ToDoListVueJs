<template>
    <div class="tasks">
        <template v-if="tasks.length">
            <task v-for="task in tasks" :key="task.name" :task="task">
                {{task.name}}
            </task>
        </template>
        <p v-else class="no-task">
            Sua vida esta em dia
        </p>
    </div>
</template>

<script>
import task from "./task.vue";
export default {
    name: "taskGrid",
    components:{ task },
    props:{
        tasks: {type:Array, required:true}
    }
}
</script>

<style scoped>
    .task-grid{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .task-grid .task{
        margin: 10px;
    }

    .no-task{
        color: #aaa;
        font-size: 1.7rem;
    }

</style>