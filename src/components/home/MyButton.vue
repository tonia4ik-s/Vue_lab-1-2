<template>
  <b-button
      type="submit"
      variant="primary"
      :disabled="isDisabled"
  >
    Submit
  </b-button>
</template>

<script>
export default {
  name: 'MyButton',
  props: {
    isDisabled: Boolean
  }
}
</script>