<template>
  <q-page class="row items-center justify-evenly">
    <div>
      <h3 class="title">Title</h3>
      <q-input v-model="input" label="input" />
      <example-component
        title="Example component"
        active
        :todos="todos"
        :meta="meta"
      />
    </div>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models'
import ExampleComponent from 'components/ExampleComponent.vue'
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  components: { ExampleComponent },
  setup () {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1'
      },
      {
        id: 2,
        content: 'ct2'
      },
      {
        id: 3,
        content: 'ct3'
      },
      {
        id: 4,
        content: 'ct4'
      },
      {
        id: 5,
        content: 'ct5'
      }
    ])
    const meta = ref<Meta>({
      totalCount: 1200
    })
    const input = ref<string>()
    return { todos, meta, input }
  }
})
</script>
<style scoped>
.title {
  font-size: 1.3em;
  color: red;
}
</style>
