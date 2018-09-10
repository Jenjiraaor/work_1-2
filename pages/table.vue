<template>
<div>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1"
>
    <template slot="items" slot-scope="props">
      <td>{{ props.item.s_id }}</td>
      <td class="text-xs-center">{{ props.item.s_name }}</td>
      <td class="text-xs-center">{{ props.item.s_size }}</td>
      <td class="text-xs-center">{{ props.item.s_color }}</td>
    </template>
    <template slot="pageText" slot-scope="props">
      Lignes {{ props.pageStart }} - {{ props.pageStop }} de {{ props.itemsLength }}
    </template>
  </v-data-table>
  <div>
      <v-btn color="success">แก้ไข</v-btn>
      <v-btn color="error">เพิ่ม</v-btn>
    </div>
    </div>
</template>
<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 's_id',
            align: 'left',
            sortable: false,
            value: 's_id'
          },
          { text: 's_name', value: 's_name',align: 'center' },
          { text: 's_size ', value: 's_size ',align: 'center' },
          { text: 's_color (g)', value: 's_color',align: 'center' },
        ],
        desserts: [],
      }
    },
    async created() {
    this.getstudent()
  }, 
methods: {
    async getstudent() {
      let res = await this.$http.get('http://127.0.0.1/php_test/list-student.php')
      this.desserts = res.data.student
    },
},
  }
</script>