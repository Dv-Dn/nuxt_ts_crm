<script lang="ts">
import { Component, Prop, Vue } from 'nuxt-property-decorator'
@Component
export default class Table extends Vue {
  @Prop({ required: false }) title!: string
  @Prop({ required: false }) placeholder!: string
  @Prop({ required: true }) head!: string[]
  @Prop({ required: true }) rows!: string[][]
  @Prop({ default: '100%' }) maxWidth!: string
}
</script>

<template>
  <table class="table" :style="{ 'max-width': maxWidth }">
    <caption v-if="title" class="table__title">
      {{
        title
      }}
    </caption>
    <tr class="table__head-row">
      <th :key="item" v-for="item in head" class="table__th">{{ item }}</th>
    </tr>
    <!-- placeholder value -->
    <tr
      v-if="(rows.length === 0 || rows[0].length === 0) && placeholder != ''"
      class="table__tr"
    >
      <td
        :key="'--' + i"
        v-for="(a, n, i) in head"
        v-html="i === 0 ? placeholder : ''"
        class="table__td"
      ></td>
    </tr>
    <!-- Rows -->
    <tr
      :key="'-' + i"
      v-for="(row, i) of rows"
      v-show="row.length !== 0"
      class="table__tr"
    >
      <td :key="item + i" v-for="(item, i) in row" class="table__td">
        {{ item }}
      </td>
    </tr>
  </table>
</template>
