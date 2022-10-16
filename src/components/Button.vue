<template>
  <button :style="{background: color}" class="btn">{{text}}</button>
</template>
<script>
export default {
  name: 'Button',
  props: {
    text: String,
    color: String
  }
  
}
</script>

<style>
.btn {
  background: green;
  color: #fff;
  font-size: 14px;
  font-weight: 400;
  outline: none;
  border: none;
  border-radius: 5px;
  padding: 10px 15px;
}
</style>