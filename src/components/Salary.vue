<template>
  <section>
    <img v-bind:src="picture" />
    <h1>ชื่อพนักงาน : {{ getFullName }}</h1>
    <h2>ชื่อเล่น : {{ nickname }}</h2>
    <h1>อายุ : {{ age }} ปี</h1>
    <h1>เงินเดือน : {{ salary }}</h1>
    <h1>รายได้ต่อปี : {{ getIncome }}</h1>
    <h1>ตำแหน่งงาน : {{ getDepartment }}</h1>
    <button @click="addSalary">ขอเพิ่มเงิน</button>
    <button @click="reduceSalary">ลดจำนวนเงิน</button>
        <hr />
        <button @click="toggleisVisible">
      {{ isVisible ? "ซ่อน" : "แสดง" }}รายละเอียด
    </button>
    <article v-show="isVisible">
      <div>
        <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
        <p v-else>งานอดิเรก :</p>
        <ul>
          <li v-for="(item, index) in hobby" :key="index">
            {{ index + 1 }}.{{ item }}
          </li>
        </ul>
      </div>
      <p>ข้อมูลทั่วไป :</p>
      <ul>
        <li v-for="(item, key) in general" :key="key">{{ key }}:{{ item }}</li>
      </ul>
      <h1>
        <a :href="facebook" target="_blank">
          <img
            src="https://cdn-icons-png.flaticon.com/128/1402/1402183.png"
            alt=""
            height="50"
            width="50"
          />
        </a>
        <a :href="github" target="_blank">
          <img
            src="https://cdn-icons-png.flaticon.com/128/919/919847.png"
            alt=""
            height="50"
            width="50"
          />
        </a>
      </h1>
    </article>
  </section>
</template>

<script>
export default {
      data() {
    return {
      firstname: "chanchai",
      lastname: "janhom",
      nickname: "heart",
      age: "23",
      picture: "https://cdn-icons-png.flaticon.com/128/8288/8288618.png",
      facebook: "https://www.facebook.com/chanchai.janhom.7?locale=th_TH",
      github: "https://github.com/Chanchai-Heart",
      hobby: [
        "ดูหนัง",
        "ออกกําลังกาย",
        "อ่านหนังสือ",
        "ฟังเพลง",
        "เล่นเกม",
        "ดูบอล",
      ],
      general: { gender: "ชาย", weight: 65, height: 180, blood: "B" },
      isVisible: false,
      salary: 15000,//เงินเดือน
    };
  },
  methods: {
    toggleisVisible() {
      this.isVisible = !this.isVisible;
    },
    addSalary() {
      this.salary += 2500;//เพิ่มเงิน
    },
    reduceSalary() {
      this.salary -= 2500;//ลดเงิน
    },
  },
  computed: {
    getFullName() {
      return `${this.firstname} ${this.lastname}`;
    },
    getIncome() {
      return this.salary * 12;
    },
    getDepartment() {
      return this.salary >= 35000 ? "Project Manager" : "Programmer";//เงินเดือนมากกว่าหรือเท่ากับ 35000
    },
  },
  watch: {//ตรวจสอบเงินเดือน
    salary(Value) {
      if (Value > 50000) {
        alert("เงินเดือนเกินกําหนด");//แจ้งเตือนเงินเดือนเกินกําหนด
        setTimeout(() => {
          this.salary = 50000;//รีเซ็ตเงินเดือน
        }, 1000);//หน่วงเวลา 1 วินาที
      }
    },
  },
}
</script>

<style>

</style>