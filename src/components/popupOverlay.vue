<template>
  <div class="PopupOverlay" @click="$emit('close')"></div>
</template>

<script>
export default {
  name: 'PopupOverlay',
}
</script>

<style>
.PopupOverlay {
  overflow: auto;
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-color: rgba(27, 27, 27, 0.8);
}
</style>
