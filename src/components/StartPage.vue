<template>
  <div class="root-box">
    <div class="box-container">
      <h1 class="hello">Hello!</h1>
      <div class="box-text">
        <input
          class="input-text"
          type="text"
          placeholder="enter login"
          v-bind:value="inputName"
          v-on:input="changeName"
        />
        <input
          class="input-text"
          type="text"
          placeholder="enter password to enter"
        />
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
export default {
  components: {
    popupWelcome,
    popuRegister,
  },

  data() {
    return {
      inputName: '',
      welcomeName: '',
      isPopupWelVisible: false,
      isPopupRegVisible: false,
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
      console.log(5)
      setTimeout(() => {
        this.isPopupRegVisible = false
      }, 5000)
    },
  },
}
</script>
