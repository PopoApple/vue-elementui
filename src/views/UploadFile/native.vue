<template>
  <div>
    <el-upload
      ref="upload"
      action="xxx"
      :file-list="fileList"
      :before-upload="beforeUpload"
      :http-request="handleUpolad"
      multiple
      :on-change="handleChange"
      :show-file-list="false"
    >
      <el-button slot="trigger">选取文件</el-button>
      <el-button
        style="margin-left: 10px"
        size="small"
        type="success"
        @click="submitUpload"
      >
        上传到服务器
      </el-button>
    </el-upload>
    <div v-for="item in fileList" :key="item.uid">{{ item.name }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fileList: [],
      actionType: null,
    }
  },
  methods: {
    submitUpload() {
      console.log('111111111111')
      this.actionType = 'upload'
      this.$refs.upload.submit()
      console.log('22222222222')
    },
    beforeUpload(file) {
      console.log('beforeUpload:', file)
      if (this.actionType !== 'upload') {
        console.log('校验...')
        this.fileList = [...this.fileList, { uid: file.uid, name: file.name }]
        return false
      }
      console.log('xxxxxxxxxxxxxx')
      this.actionType = null
      return true
    },
    handleUpolad(a, b, c) {
      console.log('handleUpolad:', a, b, c)
    },
    handleChange(file, fileList) {
      console.log('handleChange', file, fileList, fileList.length)
      //this.fileList = fileList
    }
  },
};
</script>
