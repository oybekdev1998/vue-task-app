<template>
  <div class="header">
    <h1>{{title}}</h1>
    <Button text="Add Task" color="green" />
  </div>
</template>

<script>
import Button from './Button.vue';
export default {
    name: "Header",
    props: {
      title: String
    },
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