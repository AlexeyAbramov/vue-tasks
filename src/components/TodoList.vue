<template>
  <ul>
    <TodoItem v-for="(task,index) in tasks" :key="task.id"
                                            :task="task"
                                            :index="index"
                                            @removeTask="removeTask($event)" />
  </ul>
</template>

<script>
import TodoItem from '@/components/TodoItem';

export default {
  props:{
    tasks: Array
  },
  data() {
    return {};
  },
  methods: {
    removeTask(e){
      this.$emit('removeTask', e)
    }
  },
  components: {
    TodoItem
  }
};
</script>

<style scoped>
    ul{
        list-style: none;

        margin: 0;
        padding: 0;
    }
</style>