<template>
  <h1>this is home to all!!</h1>
  <p>
    name :{{ name }}
    <br />
    age : {{ age }}
    <br />
    gender : {{ gender }}
    <br />
    salary : {{ salary }}
    <br />
    job descrpition : 
    <JobList :jobs="jobs" />
  </p>
  <button @click="changeName('bhongade sharanya', 'female')">
    change my Name
  </button>
  <button @click="changeAge(33, '1353464')">change my Name</button>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "@vue/runtime-core";
import type  Job from "@/types/Job";
import JobList from './JobList.vue';

export default defineComponent({
  name : 'NewsFeed',
  componenets :{JobList},
  setup() {
    const state = reactive({
      name: "sharanya",
      age: 34 as string | number,
    });

    const gender = ref("male");
    const salary = ref<number | string>(10000000);

    const jobs = ref<Job[]>([
      {
        title: "farm worker",
        location: "lon lon ranch",
        salary: 30000,
        id: "1",
      },
      {
        title: "quarryman",
        location: "death mountain",
        salary: 40000,
        id: "2",
      },
      {
        title: "flute player",
        location: "the lost woods",
        salary: 35000,
        id: "3",
      },
      { title: "fisherman", location: "lake hylia", salary: 21000, id: "4" },
      {
        title: "prison guard",
        location: "gerudo valley",
        salary: 32000,
        id: "5",
      },
    ]);

    return { ...toRefs(state), gender, salary,jobs };
  },
  methods: {
    changeName(name: string, gender: string) {
      this.name = name;
      this.gender = gender;
      return name;
    },
    changeAge(age: string | number, salary: string | number) {
      this.age = age;
      this.salary = salary;
    },
  },
});
</script>

<style>
</style>