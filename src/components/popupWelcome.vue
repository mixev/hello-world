<template>
  <div id="id01">
    <testPopup @click="$emit('close')" />
    <div class="Welcome-module">Welcome name!</div>
  </div>
</template>

<script>
import testPopup from './testPopup'

export default {
  components: {
    testPopup,
  },
  name: 'popupWelcome',
  props: {},

  data() {
    return {}
  },
  methods: {
    closePopup() {
      this.$emit('close')
    },
  },
}
</script>

<style scoped>
.rm {
  background: brown;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}
.done {
  text-decoration: line-through;
}
.Welcome-module {
  width: 321px;
  height: 249px;
  background-color: white;
  color: #9b8db3;
  text-align: center;
  border-radius: 40px;
  position: fixed;
  left: 30%;
  top: 30%;
  box-sizing: border-box;
  box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.25);
  z-index: 1;
  font-size: 29px;
  -webkit-animation: fadeIn 1s;
  animation: fadeIn 1s;
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
