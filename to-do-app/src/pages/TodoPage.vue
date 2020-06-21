<template>
  <q-page class="q-pa-md">
    <q-list
      bordered
      separator
    >

      <q-item
        v-for="task in tasks"
        :key="task.id"
        @click="task.completed = !task.completed"
        clickable
        :class="!task.completed ? 'bg-lime-1' : 'bg-green-2'"
        v-ripple
      >
        <q-item-section
          side
          top
        >
          <q-checkbox v-model="task.completed" />
        </q-item-section>

        <q-item-section>
          <q-item-label :class="{'text-strikethrough' : task.completed}">{{ task.name }}</q-item-label>
        </q-item-section>

        <q-item-section side>

          <div class="row">
            <div class="column justify-center">
              <q-icon
                name="event"
                size="18px"
                class="q-mr-xs"
              />
            </div>
            <div class="column">
              <q-item-label
                class="row justify-end"
                caption
              > {{ task.dueDate }} </q-item-label>
              <q-item-label
                class="row justify-end"
                caption
              > <small>{{ task.dueTime }}</small> </q-item-label>
            </div>
          </div>

        </q-item-section>

      </q-item>

    </q-list>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      tasks: [
        {
          id: 1,
          name: 'Grocery shopping',
          completed: false,
          dueDate: '2020/06/22',
          dueTime: '18:00'
        },
        {
          id: 2,
          name: 'Do 4 leetcode problems',
          completed: false,
          dueDate: '2020/06/21',
          dueTime: '22:00'
        },
        {
          id: 3,
          name: 'Exercise',
          completed: false,
          dueDate: '2020/06/22',
          dueTime: '21:00'
        }
      ]
    }
  }
}
</script>

<style>
</style>
