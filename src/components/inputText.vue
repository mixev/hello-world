<template>
  <input
    class="reg-input -text"
    type="text"
    :value="value"
    :placeholder="placeholder"
    @input.stop="addName"
  />
</template>
<script>
export default {
  name: 'inputText',
  props: {
    placeholder: String,
    value: String,
  },

  methods: {
    addName(payload) {
      this.$emit('input', payload.target.value)
    },
  },
}
</script>
