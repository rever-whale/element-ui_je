<template>
  <el-table
    :data="tableData"
    :default-sort="defaultSort"
    style="width: 100%">
    <el-table-column 
      v-for="column in columns"
      :prop="column.prop"
      :sortable="column.sortable"
      :key="column.label"
      :label="column.label"
      :formatter="column.formatter"
      :min-width="column.minWidth">
      <template v-if="column.render" v-slot="scope">
        <span v-html="column.render(scope.row)"></span>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
  export default {
    props: {
      tableData: Array,
      columns: Array,
      defaultSort: {
        type: Object,
        default: {prop: 'date', order: 'descending'}
      }
    }
  }
</script>