<template>
    <el-table
      :data="tableData"
      fit
      :default-sort = "{prop: 'groupId', order: 'descending'}"
      style="width: 100%">
      <el-table-column sortable prop="groupId" label="组号" :filters="[{text: '1', value: '1'}, {text: '2', value: '2'}, {text: '3', value: '3'}, {text: '4', value: '4'}]">        
      </el-table-column>
      <el-table-column sortable prop="groupName" label="组名" >
      </el-table-column>
      <el-table-column sortable prop="users[0].name" label="用户名" >
      </el-table-column>
      <el-table-column sortable prop="users[0].email" label="邮箱" >
      </el-table-column>
      <el-table-column sortable prop="users[0].role" label="角色" >
      </el-table-column>
      <el-table-column sortable prop="users[0].createdAt" label="创建时间" >
      </el-table-column>
    </el-table>
</template>

<script>
  export default {
    data () {
      return {
        tableData: [
          {
            groupId: 1,
            groupName: "Admin Group",
            users: [
              {
                name: "John Doe",
                email: "john.doe@example.com",
                role: "admin",
                createdAt: "2023-01-01T00:00:00Z"
              }
            ]
          }
        ]
      }
    },
    created() {
			this.getNowTime();
    },
    methods: {
			getNowTime(){
				const yy = new Date().getFullYear()
				const MM = (new Date().getMonth() + 1) < 10 ? '0' + (new             
                    Date().getMonth() + 1) : (new Date().getMonth() + 1)
				const dd = new Date().getDate() < 10 ? '0' + new Date().getDate() : new 
                    Date().getDate()
				const HH = new Date().getHours() < 10 ? '0' + new Date().getHours() : new 
                    Date().getHours()
				const mm = new Date().getMinutes() < 10 ? '0' + new Date().getMinutes() : 
                     new Date().getMinutes()
				const ss = new Date().getSeconds() < 10 ? '0' + new Date().getSeconds() : 
                     new Date().getSeconds()
        this.tableData[0].users[0].createdAt = yy + '-' + MM + '-' + dd + ' ' + HH + ':' + mm + ':' + ss;
			}
		}
  }
</script>