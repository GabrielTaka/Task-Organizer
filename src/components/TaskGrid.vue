<template>
  <div class="tasks">
    <template v-if="tasks.length">
      <Task v-for="task in tasks" :key="task.name" :task="task"></Task>
    </template>
    <template v-else>
      <p class="no-task"> Sua vida está em dia :) </p>
    </template>
  </div>
</template>

<script>
  import Task from "@/components/Task"

  export default {
    components: { Task },
    props: {
      tasks: { type: Array, required: true }
    }
  }
</script>

<style scoped>
  .tasks {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }

  .tasks .task {
    margin: 10px;
  }

  .no-task {
    color: #AAA;
    font-size: 1.7rem;
  }
</style>