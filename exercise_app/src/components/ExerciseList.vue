<template>
  <div id="exercise-list">
    <table>
      <thead>
        <tr>
          <th>Exercise Name</th>
          <th>Date of Exercise</th>
          <th>Distance(miles)</th>
          <th>Calories Burned</th>
          <th>Time(minutes)</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="exercise in exercises" :key="exercise.id">

          <td v-if="editing === exercise.id">
          <input type="text" v-model="exercise.name" />
          </td>
        <td v-else>{{ exercise.name }}</td>

        <td v-if="editing === exercise.id">
          <input type="text" v-model="exercise.date" />
          </td>
        <td v-else>{{ exercise.date }}</td>

        <td v-if="editing === exercise.id">
          <input type="text" v-model="exercise.distance" />
          </td>
        <td v-else>{{ exercise.distance }}</td>

        <td v-if="editing === exercise.id">
          <input type="text" v-model="exercise.calories" />
          </td>
        <td v-else>{{ exercise.calories }}</td>

        <td v-if="editing === exercise.id">
          <input type="text" v-model="exercise.time" />
          </td>
        <td v-else>{{ exercise.time }}</td>


        <td v-if="editing === exercise.id">
          <button @click="editing = null">Save</button>
          <button @click="editing = null">Cancel</button>
        </td>


        <td class="buttons">
          <button @click="handleEdit(exercise.id)">Edit</button>
          <button @click="$emit('past', exercise), $emit('delete', exercise.id)">Delete</button>
        </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'exercise-list',
  props: {
    exercises: Array,
  },
  data() {
    return {
      editing: null
    }
  },
  methods: {
    handleEdit(id) {
      this.editing = id
    }
  }
}
</script>






<style scoped>
th, td {
  border: 1px solid;
  padding: 15px;
  color: black;
}
table {
  margin-top: 35px;
  background-color: rgb(178, 230, 230);
  border-radius: 5px;
  padding: 15px;
}
.buttons {
  display: flex;
  flex-direction: column;
  border: none;
}
button {
  margin: 5px;
}
button:hover {
  background-color: blanchedalmond;
  color: black;
}
td input {
  padding: 3%;
  background-color: rgb(175, 168, 158);
  border: none;
}</style>
