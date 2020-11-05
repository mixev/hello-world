<template>
  <div>
    <popupOverlay @click="$emit('close')" />
    <div class="register-module">
      <div class="header_reg">Registration</div>
      <div class="input-text">
        <input class="input-text --log" type="text" placeholder="enter login" />
        <input
          class="input-text --pass"
          type="text"
          placeholder="enter password"
        />
        <input
          class="input-text --pass"
          type="text"
          placeholder="enter password confirmation"
        />
      </div>
      <div class="fotter_reg">register</div>
    </div>
  </div>
</template>

<script>
import popupOverlay from './popupOverlay'

export default {
  components: {
    popupOverlay,
  },
  name: 'popupRegister',
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

<style scoped lang="scss">
$border-color: rgba(180, 175, 175, 0.82);
.header_reg {
  margin: 15px 0 20px 0;
}
.fotter_reg {
  position: absolute;
  left: 200px;
  cursor: pointer;
}
.input-text {
  margin-top: 10px;
  color: #9b8db3;
  width: 319px;
  height: 250px;
  margin-bottom: 15px;

  &.--log {
    border-radius: 34px;
    border: 1px solid $border-color;
    width: 270px;
    height: 54px;
    margin-bottom: 30px;
    padding-left: 30px;
  }
  &.--pass {
    border-radius: 34px;
    border: 1px solid $border-color;
    width: 270px;
    height: 54px;
    margin-bottom: 2px;
    padding-left: 30px;
  }
}
.register-module {
//   visibility: visible;
  width: 321px;
  height: 385px;
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
  -webkit-animation: fadeIn 0.5s;
  animation: fadeIn 0.5s;
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
