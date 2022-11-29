<template>
    <div class="job-list">
        <ul>
            <li v-for="job in jobs" :key="job.id">
            <h2>{{job.title}}</h2>
            </li>
        </ul>
    </div>
</template>


<script lang="ts">
import type Job from '@/types/Job'
import { defineComponent } from '@vue/runtime-core'
import type { PropType } from '@vue/runtime-core'



export default defineComponent({
    props : {
        jobs : {
            required :true,
            type : Array as PropType<Job[]>

        }
    },
    setup(props) {
        console.log("props",props.jobs)
    },
})
</script>
