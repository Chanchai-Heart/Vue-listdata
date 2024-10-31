<template>
  <li>
    <h1>
      ชื่อพนักงาน : {{ name }}
    </h1>
    <button class="btn" @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
    <button class="btn" @click="deleteEmployee(id)">ลบข้อมูล</button>
    <transition name="fade">
      <div v-show="isVisible">
      <p>รายได้ : {{ salary }} ตําแหน่งงาน : {{ department }}</p>
  </div>
    </transition>
  </li>
  
</template>

<script>

export default {
  name: "Person_dt",
  data() {
    return {
      message: "แสดงข้อมูลพนักงาน",
    };
  },
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 12000,
      required: true,
    },
    department: {
      type: String,
      default: "programer",
      required: true,
    },
    isVisible: {
      type: Boolean,
    },
  },
  methods: {
    showDescription(id) {
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<style scoped>

h1 {
  color: #434a42;
}
p {
  color: #434a42;

}
/* From Uiverse.io by cssbuttons-io */ 
.btn {
  position: relative;
  font-size: 12px;
  text-transform: uppercase;
  text-decoration: none;
  padding: 1em 2.5em;
  display: inline-block;
  cursor: pointer;
  border-radius: 2em;
  transition: all 0.2s;
  border: none;
  font-family: inherit;
  font-weight: 500;
  color: white;
  background-color: #434a42;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.btn:active {
  transform: translateY(-1px);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}

.btn::after {
  content: "";
  display: inline-block;
  height: 100%;
  width: 100%;
  border-radius: 100px;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  transition: all 0.4s;
}

.btn::after {
  background-color: #434a42;
}

.btn:hover::after {
  transform: scaleX(1.4) scaleY(1.6);
  opacity: 0;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 2s ease;
}
</style>