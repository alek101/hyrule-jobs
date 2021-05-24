<template>
  <div class="app">
    <p>{{name}} - {{ age }} </p>
    <button @click="changeName('Zelda')">Change Name</button>
    <button @click="changeAge(30)">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';


export default defineComponent({
  name: 'App',
  components: {},
  setup() {

    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as number | string
    // })

    // state.name = 'Alek'

    // return { ...toRefs(state)}

    const name = ref('Link')

    name.value = 'Alek'

    const age = ref <number | string>(25)

    age.value = 29

    return {name, age}
  },
  methods: {
    changeName(name: string) {
      this.name = name
    },
    changeAge(age: number) {
      this.age = age
    }
  }
});
</script>

<style>

</style>
