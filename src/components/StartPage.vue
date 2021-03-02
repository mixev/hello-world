<template>
  <div class="root-box">
    <div class="box-container">
      <h1 class="hello">Hello!</h1>
      <div class="box-text">
        <inputText
          :placeholder="textLogin"
          @inputt="addName"
          :value="inputName"
        />
        <inputText
          :placeholder="textPass"
          @inputt="addPass"
          :value="inputPass"
        />
        <buttonType
          :className="loginClass"
          :btnName="buttonLoginName"
          @click="showPopupWelcome"
        />
        <popupWelcome
          :nameLogin="welcomeName"
          v-if="isPopupWelVisible"
          @close="closePopupWelcome"
        />
      </div>
      <div class="forgot_pass">
        <buttonType :className="forgotClassfp" :btnName="buttonForgotName" />
        <buttonType
          :className="forgotClassreg"
          :btnName="buttonRegName"
          @click="showPopupRegister"
        />
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
import buttonType from './buttonType'
export default {
  components: {
    popupWelcome,
    popuRegister,
    inputText,
    buttonType,
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
      loginClass: 'login',
      buttonLoginName: 'login',
      forgotClassfp: 'forgot_pass--fp',
      buttonForgotName: 'forgot password',
      forgotClassreg: 'forgot_pass--reg',
      buttonRegName: 'register',
    }
  },
  methods: {
    addName(newName) {
      this.inputName = newName
    },
    addPass(newPass) {
      this.inputPass = newPass
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
