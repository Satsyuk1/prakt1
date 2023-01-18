
<template>
  <div class="student-input">
    <div>Ім'я студента: </div>
    <input v-model="student.name">
      <div>Здав чи не здав: </div>
    <input type="checkbox" v-model="student.isDonePr">
    <div>Виберіть группу: </div>
    <select v-model="student.group">
      <option value="RPZ 19 1/9">RPZ 19 1/9</option>
      <option value="RPZ 19 2/9">RPZ 19 2/9</option>
    </select>
  </div>
</template>

<script >
import { defineComponent } from 'vue';

export default defineComponent({
  name: "AddStudent",
  props: {
    student: {
      type: Object,
      require: true
    }
  },
});
</script>


