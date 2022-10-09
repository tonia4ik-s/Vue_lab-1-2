<template>
  <span :class="'text-' + labelClass">
    {{ textLength }} / {{ maximumLength }}
  </span>
</template>

<script>
export default {
  name: 'MyFormLabel',
  props: {
    labelClass: String,
    maximumLength: Number,
    textLength: Number
  }
}
</script>

<style scoped>
span {
  margin-bottom: 4px;
  display: flex;
  justify-content: flex-end;
}
</style>