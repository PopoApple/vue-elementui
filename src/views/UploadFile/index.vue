<template>
  <div>
    <el-button @click="handleSelectFile">选取文件</el-button>
    <el-button style="margin-left: 10px" type="success"  @click="handleUpload" >上传到服务器</el-button>
    <div v-for="item in fileList" :key="item.uid">{{ item.name }}</div>
    <input style="width: 0; height: 0" type="file" multiple ref="input" @change="handleInputChange" /> 
  </div>
</template>

<script>
export default {
  data() {
    return {
      fileList: [],
    }
  },
  methods: {
    handleSelectFile() {
      this.$refs.input.click()
    },
    handleInputChange(e) {
      console.log('handleInputChange:', e, this.$refs.input.value, this.$refs.input.files)
      let fl = this.$refs.input.files
        console.log(fl)
      for (let key in fl) {
        let f = fl[key]
        console.log(f.uid, f.name)
        this.fileList.push({ uid: f.uid, name: f.name })
      }
    },
    handleUpload() {

    }
  },
};
</script>
