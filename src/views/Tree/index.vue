<template>
 <div>
   <el-button @click="test">test</el-button>
   <el-tree node-key="id" :data="data" :props="defaultProps" @node-click="handleNodeClick" ref="tree"></el-tree>
 </div>
</template>

<script>
  export default {
    data() {
      return {
        data: [{
          id: 1,
          label: '一级 1',
          children: [{
            id: 11,
            label: '二级 1-1',
            children: [{
              label: '三级 1-1-1'
            }]
          }]
        }, {
          id: 2,
          label: '一级 2',
          children: [{
            id: 21,
            label: '二级 2-1',
            children: [{
              id: 211,
              label: '三级 2-1-1'
            }]
          }, {
            id: 22,
            label: '二级 2-2',
            children: [{
              id: 221,
              label: '三级 2-2-1'
            }]
          }]
        }, {
          id: 3,
          label: '一级 3',
          children: [{
            id: 31,
            label: '二级 3-1',
            children: [{
              id: 311,
              label: '三级 3-1-1'
            }]
          }, {
            id: 32,
            label: '二级 3-2',
            children: [{
              id: 321,
              label: '三级 3-2-1'
            }]
          }]
        }],
        defaultProps: {
          id: 'id',
          children: 'children',
          label: 'label'
        }
      };
    },
    methods: {
      test(){
        let node = this.$refs['tree'].getNode(1)
        console.log(111, node)
        node.expanded = true
        this.$refs['tree'].getNode(3).expanded = true
      },
      handleNodeClick(data) {
        console.log(data);
      }
    }
  };
</script>