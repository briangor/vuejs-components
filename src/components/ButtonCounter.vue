<template>
    <button @click="addCount" id="button-counter">You clicked {{name}}: {{ count }} times.</button>
</template>

<script>
export default {
    name: 'ButtonCounter',
    props: {
      name: String
    },
    data: function () {
    return {
      count: 0
    }
  },
  methods: {
    addCount() {
        this.count++;
    }
  }
}
</script>
<style lang="scss">
  @import '../assets/scss/style.scss';
</style>