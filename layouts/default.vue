<template>
  <div class="layout">
    <Header />
    <input type="checkbox" id="check" />
    <Sidebar :navItems="navItems" />
    <div class="content">
      <nuxt />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import Sidebar, { TNavItem } from '~/components/Sidebar.vue'
import Header from '~/components/Header.vue'

@Component({
  components: {
    Sidebar,
    Header
  }
})
export default class Default extends Vue {
  private navItems: Array<TNavItem> = [
    { to: '/', icon: 'score', name: 'Score' },
    { to: 'history', icon: 'history', name: 'History' },
    { to: 'planning', icon: 'list_alt', name: 'Planning' },
    { to: 'record', icon: 'note_add', name: 'New entry' },
    { to: 'categories', icon: 'category', name: 'Categories' }
  ]
}
</script>
