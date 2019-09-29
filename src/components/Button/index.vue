<template>
  <button @click="onClick" id="uioi-button" class="uioi-button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'uioi-button',
  methods: {
    onClick() {
      console.log('====>  :');
      const API_URL = 'http://yapi.demo.qunar.com/mock/99330/get/user?id=100';
      this.axios.get(API_URL).then((res => {
        console.log('res.data :', res.data);
      }))
    }
  }
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
  cursor: pointer;
}
</style>