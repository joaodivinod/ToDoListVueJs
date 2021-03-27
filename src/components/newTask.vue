<template>
    <div class="new-task">
        <input v-model = "name" type="text" @keydown.enter="add()">
        <button @click="add()">+</button>
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

</style>