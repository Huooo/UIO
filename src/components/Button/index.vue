<template>
  <button id="uioi-button" class="uioi-button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'uioi-button'
}
</script>

<style scoped>
.uioi-button {
  border: none;
  outline: none;

  width: 100px;
  height: 30px;
  color: #fff;
  text-align: center;
  line-height: 30px;
  background-color: #333;
  border-radius: 50px;
}
</style>