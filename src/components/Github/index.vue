<template>
  <div>
    <svg-icon icon-class="download" @click="click" />
  </div>
</template>

<script>
export default {
  name: 'Github',
  methods: {
    click() {
      window.open('https://github.com/DengSinkiang/sk-admin', '_blank')
    }
  }
}
</script>
