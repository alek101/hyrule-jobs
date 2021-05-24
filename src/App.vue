<template>
  <div class="app">
    <p>{{name}} - {{ age }} </p>
    <button @click="changeName('Zelda')">Change Name</button>
    <button @click="changeAge(30)">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
  name: 'App',
  components: {},
  data() {
    return {
      name: 'Link',
      age: 25 as number | string
    }
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
