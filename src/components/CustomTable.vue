<template>
  <el-table
    :data="tableData"
    style="width: 100%">
    <el-table-column 
      v-for="column in columns"
      :prop="column.prop"
      :key="column.label"
      :label="column.label"
      :formatter="column.formatter"
      :min-width="column.minWidth">
      <template v-if="column.render" v-slot="scope">
        <span v-html="column.render(scope.row)"></span>
        <!-- <span v-html="renderTemplate(column.render, scope.row, column.formatter)"></span> -->
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
  export default {
    props: ['tableData', 'columns'],
    methods: {
      renderTemplate (render, row, formatter) {
        if (formatter && typeof formatter === 'function') {
          row = Object.assign({}, row, formatter(row))
        }

        return render(row)
      }
    }
  }
</script>