<template>
  <section>
    <div class="page-title">
      <h2 class="h2">Score</h2>
    </div>
    <div class="home-block">
      <Table :head="table1.thead" :rows="table1.tbody" :title="table1.title" />

      <Table :head="table2.thead" :rows="table2.tbody" :title="table2.title" />
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import Button from '~/components/Button.vue'
import Table from '~/components/Table.vue'

export type TableType = {
  title: string
  thead: string[]
  tbody: string[][]
}
@Component({
  components: {
    Button,
    Table
  }
})
export default class Home extends Vue {
  public text: string = ''
  public table1: TableType = {
    title: 'Курс',
    thead: ['Валюта'],
    tbody: [['руб']]
  }
  public table2: TableType = {
    title: 'Курс валют',
    thead: ['Валюта', 'Курс', 'Дата'],
    tbody: [['руб', '12121', '12.12.12']]
  }
}
</script>
