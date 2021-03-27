<template>
<div class="task" :class="stateClass">
    <span @click="$emit('taskDeled',task)" class="close">X</span>
    <p>{{task.name}}</p>
</div>
</template>

<script>
export default {
name: "task",
  props:{
    task:{type:Object,require: true}
  },
  computed:{
    stateClass(){
      return{
        pending :this.task.pending,
        done:!this.task.pending,
      }
    }
  }
}
</script>

<style scoped>
  .task{
      position: relative;
    box-sizing: border-box;
    width: 350px;
    height: 150px;
    padding: 10px;
    border-radius: 2rem;
    font-weight: 300;
    cursor: pointer;
    user-select: none;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .pending{
    border-left:12px solid #b73229 ;
    background-color: #b73229;
  }
  .done{
    color: #ddd;
    border-left: 12px solid  #0a8f08;
    background-color:#0a8f08;
    text-decoration: line-through;
  }
  .pending .close{
      background-color: #b73229;
  }
  .done .close{
      background-color: #0a8f08;
  }
  .close{
      position: absolute;
      right: 10px;
      top: 10px;
      font-size: 0.9rem;
      font-weight:600;
      height: 20px;
      width: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
  }
</style>