<template>
  <template v-if="!isEdit">
    <td>{{item.name}}</td>
    <td><input type="checkbox" v-model="item.isDonePr"></td>
    <td>{{item.group}}</td>
    <td><a class="btn btn-outline-danger" href = "#" @click="$emit('delete', item._id)">Видалити</a></td>
    <td><a  class="btn btn-outline-success" href="#" @click="$emit('edit', item)">Змінити</a></td>
  </template>
  <StudentInput :student="newStudent" v-else></StudentInput>
  <td v-if="!isEdit"><a class="btn btn-outline-success" href="#" @click="isEdit = !isEdit, newStudent = item">Змінити2</a></td>
  <td v-else><a  class="btn btn-outline-success" href="#" @click="updateStudent(newStudent)">Змінити</a></td>

</template>

<script>
import { defineComponent } from 'vue';
import StudentInput from './StudentInput.vue';
export default defineComponent({
  name: "StudentShow",
  components: {
    StudentInput
  },
  props: {
    item: {
      type: Object,
      require: true
    }
  },
  data() {
    return {
      isEdit: false,
      newStudent: {},
    };
  },
  methods: {
    deleteStudent(studId) {
      this.$parent.deleteStudent(studId);
    },
    updateStudent(newStudent) {
      this.isEdit = !this.isEdit;
      this.$parent.updateStudent(newStudent);
    }
  }

});

</script>