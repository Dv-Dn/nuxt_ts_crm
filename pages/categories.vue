<template>
  <section>
    <div class="page-title">
      <h2 class="h2">Categories</h2>
    </div>

    <div class="categories-block">
      <div class="categories-block__item">
        <h3 class="h3">Create</h3>
        <Input v-model="createName" placeholder="Name" />
        <Input v-model="createLimit" placeholder="Limit" type="number" />
        <Button value="Create" />
      </div>
      <div class="categories-block__item">
        <h3 class="h3">Edit</h3>

        <Input v-model="updateName" placeholder="Name" />
        <Input v-model="updateLimit" placeholder="Limit" type="number" />
        <Button value="Update" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import Input from '~/components/Input.vue'
import Button from '~/components/Button.vue'

@Component({
  components: {
    Input,
    Button
  }
})
export default class Categories extends Vue {
  public createName: string = ''
  public createLimit: string = ''

  public updateName: string = ''
  public updateLimit: string = ''
}
</script>
