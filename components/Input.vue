<template>
  <label class="textInput">
    <input
      class="textInput__field"
      :type="type"
      :value="value"
      ref="input"
      :placeholder="placeholder"
      @input="input($event.target.value)"
    />
  </label>
</template>
<script lang="ts">
import { Vue, Component, Prop, Emit } from 'nuxt-property-decorator'
export type TInput = string | number
@Component
export default class Input extends Vue {
  @Prop({ required: true }) value!: string
  @Prop({ default: 'text' }) type!: string
  @Prop() placeholder!: string

  @Emit()
  input(e: TInput): TInput {
    return e
  }
}
</script>
