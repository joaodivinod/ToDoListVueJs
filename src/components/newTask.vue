<template>
    <div class="new-task">
        <input v-model="name" type="text" @keydown.enter="add" class="form-elment" placeholder="Nova Tarefa">
        <button class="form-element" @click="add">+</button>
    </div>
</template>

<script>
export default {
    name: "newTask",
    data(){
        return{
            name:''
        }
    },
    methods:{
        add(){
            this.$emit('taskAdd',{name:this.name})
            this.name = ''
        }
    }
}
</script>

<style scoped>
    .new-task{
        margin: 35px;

    }

    .form-element{
        outline: none;
        font-size: 2rem;
        border:1px solid #fff;
        padding: 5px 10px 8px;
        color: #fff;
    }

    input.form-element{
        width: 500px;
        background: #fff2;
        border-top-left-radius:8px ;
        border-bottom-left-radius:8px ;
    }
    button.form-element{
        border-left: none;
        background: #2196f3;
        border-top-right-radius: 8px;

    }

</style>