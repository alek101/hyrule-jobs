<template>
  <div class="app">
    
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue'
import Job from './types/Job'


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

    // const name = ref('Link')

    // name.value = 'Alek'

    // const age = ref <number | string>(25)

    // age.value = 29

    // return {name, age}

    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])

    return {jobs}
  },
  methods: {
    
  }
});
</script>

<style>

</style>
