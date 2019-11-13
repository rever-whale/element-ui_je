<template>
  <div>
    <custom-table 
      :tableData="tableData"
      :columns="columns" />
    <origin-table />
  </div>
</template>

<script>
import CustomTable from "./CustomTable";
import OriginTable from './OriginTable';
export default {
  components: { CustomTable, OriginTable },
  data() {
    return {
      tableData: [
        {
          date: "2016-05-03",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles",
        },
        {
          date: "2016-05-02",
          name: "Alice",
          address: "No. 1891123123, Grove St, Los Angeles",
        },
        {
          date: "2016-05-04",
          name: "Teddy",
          address: "No. 18911, Grove St, Los Angeles",
        },
        {
          date: "2016-05-01",
          name: "Put",
          address: "No. 1890000, Grove St, Los Angeles",
        }
      ],
      columns: [
        {
          prop: "date",
          label: "DATE",
          minWidth: "180px",
          sortable: true,
          render: ({ date }) => { 
            const dateArr = date.split('-')
            const CALENDAR_STRING = ['년', '월', '일']
            const htmlStr = dateArr.map((el, idx) => `${el}${CALENDAR_STRING[idx]} `).join('')
            
            return `
              <h3>${htmlStr} 템플릿 테스트</h3>
            `
          }
        },
        {
          prop: "name",
          label: "NAME",
          sortable: true,
          minWidth: "180px",
        },
        {
          prop: "address",
          label: "ADDRESS",
          sortable: true,
          minWidth: "180px",
          render: (scope) => `
            <div>
              <p @click="scope.func">hello world</p>
              <h5>${scope.address}</h5>
            </div>
          `
        }
      ]
    };
  }
};
</script>

