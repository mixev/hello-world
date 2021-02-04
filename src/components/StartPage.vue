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
