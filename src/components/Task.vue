<template>
  <div class="container">
    <div class="task">
      <h3 class="text">{{task.text}}</h3>
      <p class="day">{{task.day}}</p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  }
}

</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  width: 100%;
  border: none;
  height: 100%; 
}

.task {
  border: 1px solid #ccc;
  border-radius: 5px;
  height: 60px;
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.text {
  font-size: 16px;
}

.day {
  font-size: 14px;
  margin-top: 5px;
}
</style>