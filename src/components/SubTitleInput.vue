<template>
  <input
    @input="emitTitle"
    class="sub-title"
    type="text"
  >
</template>

<script lang="ts">
import { defineComponent, SetupContext } from 'vue'

export default defineComponent({
  setup (context: SetupContext) {
    const emitTitle = (evt) => {
      console.log(evt.target.value)
      context.emit('change', evt.target.value)
    }
    return {
      emitTitle
    }
  }
})
</script>

<style>
.sub-title {

}
</style>