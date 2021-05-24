<template>
    <div class="job-list">
        <p>Ordered by {{order}}</p>
        <ul>
            <li v-for="job in orderedJobs" :key="job.id">
                <h2>{{ job.title }} in {{job.location}}</h2>
                <div class="salary">
                    <p> {{ job.salary }} rupees</p>
                </div>
                <div class="description">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam eum, distinctio quo velit odio dolorem? Perferendis excepturi earum maxime dolorum architecto itaque facilis. Alias, reiciendis earum assumenda eligendi excepturi distinctio!
                    Dolor atque beatae, cum aliquam nobis nihil earum officiis dolore sint possimus! Modi, esse consequuntur earum saepe, reiciendis odio, aut velit cum ullam dolores numquam alias veritatis optio deserunt dolorem.
                    Deleniti qui, tenetur adipisci assumenda consequatur eveniet animi ipsum, officiis, iusto ad voluptates dignissimos neque. Porro quisquam soluta, suscipit libero aperiam aliquam nulla laborum dicta repudiandae quo mollitia excepturi rem.
                    Deserunt, totam. Totam eos modi voluptates nam tempora corporis doloremque saepe explicabo nesciunt odio, earum tempore dolore in eius provident cumque! Nesciunt dolores suscipit quo sint ipsa earum non dolorem!
                    Odio excepturi eius, corrupti quo optio architecto incidunt perspiciatis consequuntur nulla, temporibus voluptas, ea distinctio sequi expedita. Odit sint nulla placeat inventore ullam, laudantium velit asperiores iusto, incidunt, itaque harum?</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import Job from '@/types/Job'
import OrderTerm from '@/types/OrderTerm'

export default defineComponent({
    props: {
        jobs: {
            requred: true,
            type: Array as PropType<Job[]>
        },
        order: {
            requred: true,
            type: String as PropType<OrderTerm>
        }
    },
    setup(props) {
        const orderedJobs = computed(() => {
            return [...props.jobs].sort((a: Job, b: Job)=>{
                return a[props.order] > b[props.order] ? 1 : -1;
            })
        })

        return {orderedJobs}
    }
})
</script>

<style scoped>
    .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>