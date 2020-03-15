<template>
  <div class="container">
    <div class="row">
      <div class="col-4 mt-4 text-center">
        <h1>Tasks</h1>
        <hr />
        <AddTask :id="currentId" @addTask="add($event)" />
        <TodoList :tasks="tasks" @removeTask="removeTask($event)" />
      </div>
    </div>
  </div>
</template>

<script>
import AddTask from '@/components/AddTask';
import TodoList from '@/components/TodoList';

export default {
  data() {
    return {
      currentId: 1,
      tasks: []
    };
  },
  methods: {
    add(e) {
      console.log(e);
      this.tasks.push({
        id: this.currentId++,
        text: e,
        completed: false
      });
    },
    removeTask(e) {
       this.tasks = this.tasks.filter(i => i.id != e);
    },
  },
  computed: {
      
  },
  components: {
    AddTask,
    TodoList
  }
};
</script>
