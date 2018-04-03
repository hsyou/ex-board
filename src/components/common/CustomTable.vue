<template>
  <div>
    <table class="table">
      <thead>
        <th v-for="(column,index) in columns" :key="index" :width="column.width">
          {{column.label}}
        </th>
      </thead>
      <tbody>
        <tr v-for="(row,index) in rows" :key="index" @click="_trClick(row)">
          <td v-for="(column,index) in columns" :key="index">
            {{row[column.field]}}
          </td>
        </tr>
      </tbody>
      <tfoot>
      </tfoot>
    </table>
  </div>
</template>

<script>
import bootstrap from 'bootstrap'
export default {
  name: 'custom-table',
  props: {
    rows: {
      type: Array
    },
    columns: {
      type: Array
    }
  },
  methods: {
    _trClick: function (row) {
      this.$emit('trClick',row)
    }
  }
}
</script>

<style>

</style>
