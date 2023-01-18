<template>
  
  <div class="student-input">
    <table class="table table-striped text-center">
    <input v-model="student.name">
    <input type="checkbox" v-model="student.isDonePr">
    <select v-model="student.group">
      <option value="RPZ 19 1/9">RPZ 19 1/9</option>
      <option value="RPZ 19 2/9">RPZ 19 2/9</option>
    </select>
      </table>
  </div>

</template>

<script >
import { defineComponent } from 'vue';

export default defineComponent({
  name: "StudentInput",
  props: {
    student: {
      type: Object,
      require: true
    }
  },
});
</script>


