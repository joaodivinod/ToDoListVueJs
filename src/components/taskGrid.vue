<template>

  <div class="tasks-grid">
   <template>
     <task  v-for="task in tasks" :key="task.name" :task="task" >

     </task>
   </template>
  </div>

</template>

<script>
import task from "@/components/task.vue";
export default {
  name: "taskGrid",
  components:{task},
  props: {
    tasks:{type:Array, requirement:true}
  }
}
</script>

<style scoped>

</style>