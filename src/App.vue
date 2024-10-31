<template>
  <main>
    <header>
    <h1>ระบบจัดการข้อมูลพนักงาน</h1>
  </header>
  <section class="employee-content">
    <h2>ข้อมูลพนักงาน</h2>
    <ListData />
  </section>
  </main>
</template>

<script>
import ListData from "./components/ListData.vue";
export default {
  name: "App",
  components: {
    ListData,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

header {
 box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #434a42;
  color: white;
  text-align: center;
  width: 90%;

}
section {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  background-color: #918B76;
  padding: 1rem;
  text-align: center;
  width: 90%;

}
h2 {
  font-size: 2rem;
  border-bottom: 2px solid #3a3a3a;
  color: #434A42;
  margin-bottom: 0.5rem;
}
</style>
