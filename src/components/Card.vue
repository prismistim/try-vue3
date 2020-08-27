<template>
  <div class="card">
    <div class="title">{{ state.message }}</div>
    <span class="sub-title">{{ props.subTitle }}</span>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue"

type Props = {
  subTitle: string
}

export default defineComponent({
  props: {
    subTitle: {
      type: String,
      default: 'hogechan_dayo'
    }
  },
  setup (props: Props) {
    const state = reactive<{ message: string }>({
      message: "hogechan"
    })
    return {
      state,
      props
    }
  }
})
</script>

<style scoped>
.card {
  position: relative;
  display: inline-block;
  width: 200px;
  height: 50px;
  margin: auto;
  padding: 30px;
  border-radius: 10px;
  background-color: #fff;
}

.card::after {
  content: '';
  display: block;
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

  background-color: #42b883;
  filter: blur(10px);
  transform: translateY(10px) scale(1.0);
  mix-blend-mode: multiply;
}

.title {
  font-size: 2rem;
}
</style>