<template>
<div></div>
</template>
<script>

export default {
  name: 'hTableItem',
  props: {
    rowspan: Number,
    colspan: Number,
    title: String,
    width: Number,
    fixed: String,
    label: String,
    prop: String,
    attrs: Function,
    dict: String,
    align: String,
    className: String,
    treeOpener: Boolean,
    isObj: {
      type: Boolean,
      default: true
    },
    unit: String,
    format: Function,
    render: Function,
    sortProp: String,
    tooltip: {
      type: [Boolean, Object],
      default: false
    },
    sort: {
      type: [Boolean, String],
      default: false
    },
    placement: String,
    content: String
  },
  beforeMount() {
    this.init();
  },
  beforeDestroy() {
    this.init();
  },
  data() {
    return {};
  },
  methods: {
    init() {
      let parent = this.$parent;
      if (parent.$options._componentTag == 'Table' || parent.$options._componentTag == 'h-table') {
        parent.refresh();
      }
    }
  },
  watch: {
    title() {
      this.init();
    },
    width() {
      this.init();
    },
    fixed() {
      this.init();
    },
    label() {
      this.init();
    },
    prop() {
      this.init();
    },
    align() {
      this.init();
    }
  }
};
</script>
