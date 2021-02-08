<template>
  <div class="module">
    <popupOverlay @click="$emit('close')" />
    <div class="Welcome-module">
      <div class="text">Welcome {{ nameLogin }}!</div>
      <div class="textWait">please wait a second to login...</div>
    </div>
  </div>
</template>

<script>
import popupOverlay from './popupOverlay'

export default {
  components: {
    popupOverlay,
  },
  name: 'popupWelcome',
  props: {
    nameLogin: String,
  },

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
.module {
  overflow: auto;
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Welcome-module {
  width: 321px;
  height: 249px;
  background-color: white;
  color: #9b8db3;
  border-radius: 40px;
  position: fixed;
  box-sizing: border-box;
  box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.25);
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;

  -webkit-animation: fadeIn 0.5s;
  animation: fadeIn 0.5s;
}
.text {
  width: 200px;
  height: 70px;
  text-align: center;
  font-size: 29px;
}
.textWait {
  text-align: center;
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
