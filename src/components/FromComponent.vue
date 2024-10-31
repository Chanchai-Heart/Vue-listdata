<template>
    <div>
        <h1>{{ massege }}</h1>
    </div>
</template>

<script>

export default {

  name: 'FromComponent',

  data() {
    return {
        massege : "แบบฟอร์มบันทึกข้อมูลพนักงาน"
    }
  },

}
</script>

<style scoped>
  h1{
    color: green;
  }
</style>