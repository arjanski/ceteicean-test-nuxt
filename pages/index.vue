<template>
  <div style="height: 3000px" v-html="TEI"></div>
</template>

<script>
import CETEI from '../CETEIcean/CETEI.js'
export default {
  name: 'TEITest',
  data() {
    return {
      TEI: null
    }
  },
  created() {
    var CETEIcean = new CETEI()
    var self = this
    CETEIcean.getHTML5(
      'https://gregorovius-edition.dhi-roma.it/api/letters/G000003',
      function(data) {
        console.log(data.outerHTML)
        self.TEI = data.outerHTML
      }
    )
  }
}
</script>