<template>
  <div class="root-box">
    <div class="box-container">
      <h1 class="hello">Hello!</h1>
      <div class="box-text">
        <inputText
          :text="textLogin"
          :value="inputName"
          v-on:input="changeName"
        />
        <inputText :text="textPass" :value="inputPass" />
        <div class="login" @click="showPopupWelcome">login</div>
        <popupWelcome
          v-bind:nameLogin="welcomeName"
          v-if="isPopupWelVisible"
          @close="closePopupWelcome"
        />
      </div>
      <div class="forgot_pass">
        <div class="forgot_pass--fp">forgot password</div>
        <div class="forgot_pass--reg" @click="showPopupRegister">register</div>
        <popuRegister
          v-if="isPopupRegVisible"
          @close="closePopupRegister"
          @regclose="registerAndClose"
        />
      </div>
    </div>
  </div>
</template>

<script>
import popupWelcome from './popupWelcome'
import popuRegister from './popupRegister'
import inputText from './inputText'
export default {
  components: {
    popupWelcome,
    popuRegister,
    inputText,
  },

  data() {
    return {
      inputPass: '',
      inputName: '',
      welcomeName: '',
      isPopupWelVisible: false,
      isPopupRegVisible: false,
      textLogin: 'enter login',
      textPass: 'enter password to enter',
    }
  },
  methods: {
    changeName(event) {
      this.inputName = event.target.value
    },

    showPopupWelcome() {
      this.welcomeName = this.inputName
      this.isPopupWelVisible = true
      setTimeout(() => {
        this.isPopupWelVisible = false
      }, 5000)
      this.inputName = ''
      this.inputPass = ''
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
    registerAndClose() {
      setTimeout(() => {
        this.isPopupRegVisible = false
      }, 3000)
    },
  },
}
</script>
