<template>
  <button class="button" v-on="$listeners">{{ value }}</button>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'nuxt-property-decorator'
@Component
export default class Button extends Vue {
  @Prop({ default: 'Click' }) value!: string
}
</script>
