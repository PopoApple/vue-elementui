<template>
  <div style="background: #eee; padding: 20px 10px">
    <el-button>Element按钮</el-button>
    <br/><br/>
    <van-button type="primary">主要按钮</van-button>
    <br/><br/>
    <van-button type="info">信息按钮</van-button>
    &nbsp;&nbsp;
    <van-button type="default">默认按钮</van-button>
    <br/><br/>
    <van-button type="warning">警告按钮</van-button>
    &nbsp;&nbsp;
    <van-button type="danger">危险按钮</van-button>
    <br/><br/>
    <van-button plain type="primary">朴素按钮</van-button>
    &nbsp;&nbsp;
    <van-button plain type="info">朴素按钮</van-button>
    <br/><br/>
    <field
        readonly
        clickable
        label="城市"
        :value="value"
        placeholder="选择城市"
        @click="showPicker = true"
    />
    <popup v-model="showPicker" round position="bottom">
    <picker
        show-toolbar
        :columns="columns"
        @cancel="showPicker = false"
        @confirm="onConfirm"
    />
    </popup>
  </div>
</template>

<script>
import { Button as VanButton } from 'vant'
import { Picker } from 'vant'
import { Field } from 'vant'
import { Popup } from 'vant'

export default {
    components: {
        VanButton,
        Picker,
        Field,
        Popup
    },
  data() {
    return {
        value: '',
      showPicker: false,
     columns: ['杭州', '宁波', '温州', '绍兴', '湖州', '嘉兴', '金华', '衢州'],
    }
  },
  methods: {
   onConfirm(value) {
      this.value = value;
      this.showPicker = false;
    },
  },
}
</script>
