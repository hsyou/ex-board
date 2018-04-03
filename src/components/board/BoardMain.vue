<template>
  <div>
    <custom-table
      :rows="rows"
      :columns="columns"
      @trClick="_showModal"
    ></custom-table>
    <custom-modal 
      v-show="modalFlag"
      :contents="contents"
      @close="modalFlag = false"
    ></custom-modal>
  </div>
</template>

<script>
import CustomTable from '@/components/common/CustomTable'
import CustomModal from '@/components/common/CustomModal'

export default {
  name: 'board-main',
  components: {
    CustomTable,
    CustomModal
  },
  data() {
    return {
      modalFlag: false,
      columns: [
        {
          label: '아이디',
          field: 'id',
          width: '10%'
        },
        {
          label: '제목',
          field: 'title',
          width: '60%'
        },
        {
          label: '작성자',
          field: 'writer',
          width: '15%'
        },
        {
          label: '작성일',
          field: 'createDate',
          width: '15%'
        },
      ],
      rows: [
        {
          id: 1,
          title: 'test',
          writer: 'tester',
          createDate: '2018-03-30'
        },
        {
          id: 2,
          title: 'test2',
          writer: 'tester2',
          createDate: '2018-03-30'
        },
        {
          id: 3,
          title: 'test3',
          writer: 'tester3',
          createDate: '2018-03-30'
        },
        {
          id: 4,
          title: 'test4',
          writer: 'tester4',
          createDate: '2018-03-30'
        },
        {
          id: 5,
          title: 'test5',
          writer: 'tester5',
          createDate: '2018-03-30'
        },
        {
          id: 6,
          title: 'test6',
          writer: 'tester6',
          createDate: '2018-03-30'
        }
      ],
      contents: undefined
    }
  },
  created() {

  },
  methods: {
    _showModal: function (row) {
      console.log(row)
      this.modalFlag = true
      this.contents = row
    }
  }
}
</script>

<style>

</style>
