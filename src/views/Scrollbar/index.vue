<template>
  <div>
    <el-scrollbar
      tag="ul"
      wrap-class="xxx1"
      view-class="xxx2"
      ref="scrollbar">
      <div style="background: #bbc; height: 800px">xxx</div>
    </el-scrollbar>
  </div>
</template>

<script>
import ElScrollbar from 'element-ui/lib/scrollbar.js'

export default {
components: {
    ElScrollbar,
},
  data () {
    return {

    }
  }
}
</script>
<style>
.xxx1 {
    max-height: 200px;
}
</style>

