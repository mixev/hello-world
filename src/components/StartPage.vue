<template>
  <div class="root-box">
    <div class="box-container">
      <h1 class="hello">Hello!</h1>
      <div class="box-text">
        <input class="input-text" type="text" placeholder="enter login" />
        <input
          class="input-text"
          type="text"
          placeholder="enter password to enter"
        />
        <div class="login" @click="showPopupWelcome">login</div>
        <popupWelcome v-if="isPopupWelVisible" @close="closePopupWelcome" />
      </div>
      <div class="forgot_pass">
        <div class="forgot_pass--fp">forgot password</div>
        <div class="forgot_pass--reg" @click="showPopupRegister">register</div>
        <popuRegister v-if="isPopupRegVisible" @close="closePopupRegister" />
      </div>
    </div>
  </div>
</template>

<script>
import popupWelcome from './popupWelcome'
import popuRegister from './popupRegister'
export default {
  components: {
    popupWelcome,
    popuRegister,
  },
  data() {
    return {
      isPopupWelVisible: false,
      isPopupRegVisible: false,
    }
  },
  methods: {
    showPopupWelcome() {
      this.isPopupWelVisible = true
    },
    closePopupWelcome() {
      this.isPopupWelVisible = false
    },
    showPopupRegister() {
      this.isPopupRegVisible = true
    },
    closePopupRegister() {
      this.isPopupRegVisible = false
    },
  },
}
</script>
<style scoped lang="scss">
$border-color: rgba(180, 175, 175, 0.82);
.root-box {
  height: 100%;
  display: flex;
}
.hello {
  position: relative;
  top: 15%;
  color: black;
  font-size: 50px;
  text-align: center;
}
.forgot_pass {
  color: white;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  align-self: flex-end;
  font-size: 29px;
  &--fp {
    cursor: pointer;
  }
  &--reg {
    cursor: pointer;
  }
}

.box {
  &-container {
    width: 100%;
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  &-text {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
.input-text {
  color: #9b8db3;
  border-radius: 34px;
  border: 1px solid $border-color;
  width: 302px;
  height: 54px;
  margin-bottom: 15px;
}

.login {
  color: #9b8db3;
  font-size: 39px;
  cursor: pointer;
  position: relative;
  left: 90px;
}

.login .loginText::after {
  content: '';
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border: 1px solid rgba(0, 0, 0, 0.1) transparent transparent transparent;
}
.login .show {
  visibility: visible;
}

* {
  box-sizing: border-box;
}
.input_container {
  width: 302px;
  height: 54px;
  padding: 15px;
  margin: 5px 0 5px 10px;
  display: inline-block;
  border: 1px solid rgba(39, 30, 39, 0.34);
  border-radius: 34px;
  background: rgba(255, 255, 255, 0.82);
}
.input_container:focus {
  background-color: rgba(209, 205, 205, 0.82);
  outline: none;
}
.registerbtn {
  position: relative;
  left: 180px;
  cursor: pointer;
  color: #9b8db3;
  font-size: 30px;
}
.clearfix::after {
  content: '';
  clear: both;
  display: table;
}
.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  padding-top: 50px;
}
.modal-content {
  margin: 10% auto 15% auto;
  width: 321px;
  height: 385px;
  background-color: #ffffff;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 40px;
}
.container_header {
  color: #9b8db3;
  text-align: center;
}
</style>
