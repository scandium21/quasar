<template>
  <li>
    <div>
      <slot></slot>
    </div>
    <small> {{ task.dueDate }} @ {{ task.dueTime }} </small>
    <button>Delete task</button>
  </li>
</template>

<script>
export default {
  props: ['task', 'index']
}
</script>

<style lang="scss" scoped>
</style>
