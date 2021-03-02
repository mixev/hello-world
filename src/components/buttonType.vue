<template>
  <div :class="className">{{ btnName }}</div>
</template>
<script>
export default {
  name: 'buttonType',
  props: {
    className: String,
    btnName: String,
  },
}
</script>
