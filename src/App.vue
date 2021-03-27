<template>
	<div id="app">
		<h1>Tarefas</h1>
        <new-task @taskAdd="addTask" />
        <task-grid :tasks="tasks"/>

	</div>
</template>

<script>

import newTask from "./components/newTask"
import taskGrid from "./components/taskGrid.vue";
export default {
  components:{taskGrid,newTask,},
  data(){
    return{
      tasks:[
        {name:'Lavar Louça',pending:'false'},
        {name:'Fazer compras do mês',pending: true},
      ]
    }
  },
    methods:{
      addTask(task){
          const sameName = t => t.name === task.name
          const reallyNew = this.tasks.filter(sameName).length == 0;
          if(reallyNew){
              this.tasks.push({
                  name : task.name,
                  pending: task.pending || true
              })
          }
      }
    }
}
</script>

<style>
	body {
		font-family: 'Lato', sans-serif;
		background: linear-gradient(to right, rgb(22, 34, 42), rgb(58, 96, 115));
		color: #FFF;
	}

	#app {
		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	#app h1 {
		margin-bottom: 5px;
		font-weight: 300;
		font-size: 3rem;
	}
</style>
