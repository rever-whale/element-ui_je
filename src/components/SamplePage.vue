<template>
  <div>
    <custom-table 
      :tableData="tableData"
      :columns="columns" />
  </div>
</template>

<script>
import CustomTable from "./CustomTable";
export default {
  components: { CustomTable },
  data() {
    return {
      tableData: [
        {
          date: "2016-05-03",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles"
        },
        {
          date: "2016-05-02",
          name: "Alice",
          address: "No. 1891123123, Grove St, Los Angeles"
        },
        {
          date: "2016-05-04",
          name: "Teddy",
          address: "No. 18911, Grove St, Los Angeles"
        },
        {
          date: "2016-05-01",
          name: "Put",
          address: "No. 1890000, Grove St, Los Angeles"
        }
      ],
      columns: [
        {
          prop: "date",
          label: "DATE",
          minWidth: "180px",
          render: (scope) => `
            <h3>${scope.date} 템플릿 테스트</h3>
          `
        },
        {
          prop: "name",
          label: "NAME",
          minWidth: "180px",
          // render: (scope) => `
          //   <div>
          //     <h3>${scope.name} 개별 템플릿 테스트 중</h3>
          //   </div>
          // `
        },
        {
          prop: "address",
          label: "ADDRESS",
          minWidth: "180px",
          render: (scope) => `
            <div>
              <p>hello world</p>
              <h5>${scope.address}</h5>
            </div>
          `
        }
      ]
    };
  }
};
</script>

