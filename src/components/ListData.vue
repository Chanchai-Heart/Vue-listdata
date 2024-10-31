<template>
  <ul>
    <Person_dt
      v-for="(item, index) in employees"
      :id="item.id"
      :key="index"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :isVisible="item.isVisible"
      @show="toggleVisible"
      @delete="deleteEmployee"
    ></Person_dt>
  </ul>
</template>

<script>
import Person_dt from "./Person.vue";
export default {
  name: "ListData",
  components: {
    Person_dt,
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: "อาทิตย์",
          salary: 10000,
          department: "programer",
          isVisible: false,
        },
        {
          id: 2,
          name: "อารมณ์",
          salary: 20000,
          department: "programer",
          isVisible: false,
        },
        {
          id: 3,
          name: "กิตติศักดิ์",
          salary: 30000,
          department: "programer",
          isVisible: false,
        },
        {
          id: 4,
          name: "แก้ว",
          salary: 40000,
          department: "project manager",
          isVisible: false,
        },
        {
          id: 5,
          name: "ชาลี",
          salary: 50000,
          department: "project manager",
          isVisible: false,
        },
      ],
    };
  },
  methods: {
    toggleVisible(id) {
      this.employees.map((item) => {
        if (item.id === id) {
          return (item.isVisible = !item.isVisible);
        }
      });
    },
    deleteEmployee(id) {
      this.employees = this.employees.filter((item) => item.id !== id);
    },
  },
};
</script>

<style>
ul {
  list-style-type: none;
  margin: 1rem 0;
  padding: 0;
}
</style>