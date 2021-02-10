<template>
  <div>
    <input class="reg-input -text" type="text" :placeholder="text" />
  </div>
</template>
<script>
export default {
  name: 'inputText',
  props: {
    text: String,
  },
}
</script>
