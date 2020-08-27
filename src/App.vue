<template>
  <Card :subTitle="state.subTitle"/>
  <HelloWorld msg="hogehoge fugafuga" />
  <SubTitleInput @change="changeTitle"/>
</template>

<script lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import Card from './components/Card.vue'
import SubTitleInput from './components/SubTitleInput.vue'
import { defineComponent, reactive } from 'vue'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
    Card,
    SubTitleInput
  },
  setup () {
    const state = reactive<{ subTitle: string }>({
      subTitle: "hogechan_dao"
    })
    const changeTitle = (text) => {
      console.log(text)
      state.subTitle = text.target.value
    }
    return {
      state,
      changeTitle
    }
  }
})
</script>
