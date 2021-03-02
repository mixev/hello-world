<template>
  <popupType :className="welClass">
    <template v-slot:welcome-form>
      <div class="text">Welcome {{ nameLogin }}!</div>
      <div class="textWait">please wait a second to login...</div>
    </template>
  </popupType>
</template>

<script>
import popupType from './popupType'

export default {
  components: {
    popupType,
  },
  name: 'popupWelcome',
  props: {
    nameLogin: String,
  },

  data() {
    return {
      welClass: 'popup-module --welcome',
    }
  },
  methods: {
    closePopup() {
      this.$emit('close')
    },
  },
}
</script>

<style>
.text {
  width: 200px;
  height: 70px;
  text-align: center;
  font-size: 29px;
}
.textWait {
  font-size: 18px;
}
</style>
