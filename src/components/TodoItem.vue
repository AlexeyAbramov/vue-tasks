<template>
  <li class="d-flex justify-content-between align-items-center">
      <input type="checkbox" v-model="isCompleted" @change="task.completed = isCompleted">
    <h3 :class="{line:isCompleted}">{{ index+1 }} - {{ task.text }}</h3>
    <button class="btn btn-danger" @click="removeTask(task.id)">
      Remove task
    </button>
  </li>
</template>

<script>
export default {
  props:{
    task: Object,
    index: Number
  },
  data() {
    return {
      isCompleted:''
    };
  },
  methods: {
    removeTask(id){
        this.$emit('removeTask' , id)
    }
  },
};
</script>

<style scoped>
  .line{
    text-decoration: line-through;
  }
</style>