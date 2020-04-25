<template>
  <div>
    <svg-icon icon-class="doc" @click="click" />
  </div>
</template>

<script>
export default {
  name: 'Doc',
  methods: {
    click() {
      window.open('https://www.kancloud.cn/sinkiang/skadmin_document/content', '_blank')
    }
  }
}
</script>
