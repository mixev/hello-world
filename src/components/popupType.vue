<template>
  <div class="module">
    <popupOverlay @click="$emit('close')" />
    <div :class="className">
      <slot name="regist-form"></slot>
      <slot name="welcome-form"></slot>
    </div>
  </div>
</template>
<script>
import popupOverlay from './popupOverlay'
export default {
  components: {
    popupOverlay,
  },
  name: 'popupType',
  props: {
    className: String,
  },
}
</script>
