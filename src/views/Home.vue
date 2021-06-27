<template>
  <div id="todo-list">
    <div class="todo-actions">
      <button>+ Add Task</button>
      <div class="task-status-filter">
        <div class="active">All</div>
        <div>Active</div>
        <div>Completed</div>
      </div>
    </div>
    <TodoListItem></TodoListItem>
    <TodoListItem></TodoListItem>
    <TodoListItem></TodoListItem>
  </div>
</template>

<script>
// @ is an alias to /src
import TodoListItem from "@/components/TodoListItem.vue";

export default {
  name: "Home",
  components: {
    TodoListItem,
  },
};
</script>
