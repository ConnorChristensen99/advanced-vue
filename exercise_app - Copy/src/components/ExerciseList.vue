<script setup>

defineProps({
  exercises: Array,
})

function data() {
  return {
    editing: null
  }
}

function handleDelete(id) {
  return(id)
}


function handleEdit(id) {
  return {
    editing: null
  }
}


</script>







<template>
  <div id="exercise-list">
    <table>
      <thead>
        <tr>
          <th>Exercise Name</th>
          <th>Date of Exercise</th>
          <th>Distance</th>
          <th>Calories Burned</th>
          <th>Time</th>
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
          <button @click="editExercise(exercise)">Save</button>
          <button @click="editing=null">Cancel</button>
        </td>


        <td class="buttons">
          <button @click="handleEdit(exercise.id)">Edit</button>
          <button @click="$emit('delete', handleDelete(exercise.id))">Delete</button>
        </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>






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
}</style>
