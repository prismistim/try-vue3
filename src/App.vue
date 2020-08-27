<template>
  <Card />
  <HelloWorld msg="hogehoge fugafuga" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Card
  }
}
</script>
