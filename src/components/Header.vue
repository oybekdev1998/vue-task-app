<template>
  <div class="header">
    <h1>{{title}}</h1>
    <Button
      @btn-click="$emit('toogle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </div>
</template>

<script>
import Button from './Button.vue';
export default {
    name: "Header",
    props: {
      title: String,
      showAddTask: Boolean
    },
    emits: ['toogle-add-task'],
    components: { Button }
}
</script>

<style>
.header {
  height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

h1 {
  font-size: 24px;
  color: #000;
  
}

</style>