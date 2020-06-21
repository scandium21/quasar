<template>
  <q-page padding>
    <ul>
      <task
        v-for="(task, index) in tasks"
        :key="task.id"
        :task="task"
        :index="index"
      > {{ task.name }} </task>
    </ul>
  </q-page>
</template>

<script>
// import { Task } from "../components/Task";

export default {
  data () {
    return {
      tasks: [
        {
          id: 1,
          name: 'Go to shop',
          dueDate: '2020/06/22',
          dueTime: '19:20'
        },
        {
          id: 2,
          name: 'Get bananas',
          dueDate: '2020/06/25',
          dueTime: '9:20'
        },
        {
          id: 3,
          name: 'Get apples',
          dueDate: '2020/06/22',
          dueTime: '15:20'
        }
      ]
    }
  },
  methods: {
    deleteTask (index) {
      this.tasks.splice(index, 1)
    }
  },
  components: {
    task: require('../components/Task').default
  }
}
</script>

<style>
</style>
