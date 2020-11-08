<template>
  <div id="app">
    <treeselect v-model="value" :options="options" :disable-branch-nodes="true" alwaysOpen>

    </treeselect>
  </div>
</template>

<script>
  // import the component
  import Treeselect from '@riophae/vue-treeselect'
  // import the styles
  import '@riophae/vue-treeselect/dist/vue-treeselect.css'

  export default {
    // register the component
    components: { Treeselect },
    data() {
      return {
        // define the default value
        value: null,
        // define options
        options: [ {
          id: 'a',
          label: 'a',
          children: [ {
            id: 'aa',
            label: 'aa',
          }, {
            id: 'ab',
            label: 'ab',
          } ],
        }, {
          id: 'b',
          label: 'b',
        }, {
          id: 'c',
          label: 'c',
        },
        {
          id: 'd',
          label: 'd',
        },
        {
          id: 'e',
          label: 'e',
        },
        {
          id: 'f',
          label: 'f',
        },
        {
          id: 'g',
          label: 'g',
        },
        {
          id: 'h',
          label: 'h',
        },
        {
          id: 'i',
          label: 'i',
        },
        ],
      }
    },
  }
</script>
<style>