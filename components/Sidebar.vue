<template>
  <nav class="sidebar">
    <ul class="sidebar__ul">
      <li :key="i + a.name" v-for="(a, i) in navItems" class="sidebar__li">
        <nuxt-link :to="a.to" class="sidebar__link"
          ><i class="material-icons">{{ a.icon }}</i
          >{{ a.name }}</nuxt-link
        >
      </li>
    </ul>
  </nav>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
export type TNavItem = {
  to: string
  name: string
  icon: string
}
@Component
export default class Sidebar extends Vue {
  @Prop({ required: true }) navItems!: TNavItem[]
}
</script>
