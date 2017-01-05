<template lang="pug">
  #app
    #code-mirror
    div {{ rawCode }}

  </div>
</template>

<script>
import CodeMirror from 'codemirror'

export default {
  name: 'app',
  mounted: function () {
    const appEl = document.querySelector('#code-mirror')
    this.cm = CodeMirror(appEl, {
      mode: 'javascript'
    })
    console.log(this.cm.getValue())
  },
  data: function () {
    return {
      cm: ''
    }
  },
  computed: {
    rawCode: function () {
      if (!this.cm) {
        return ''
      }
      return this.cm.getValue()
    }
  },
  components: {
  }
}
</script>

<style>
</style>
