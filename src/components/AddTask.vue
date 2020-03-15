<template>
    <form class="d-flex justify-content-between" @click.prevent="addTask">
        <input type="text" placeholder="Enter a task name" v-model.trim="value">
        <button class="btn btn-dark">Add Task</button>
    </form>
</template>

<script>
export default {
    props: {
        id: Number
    },
    data(){
        return{
            value:''
        }
    },
    methods:{
        addTask(){
            this.value != '' ? this.$emit('addTask', this.value) : this.value;
            this.value='';
        }
    }
}
</script>