<script setup>

defineProps({
  exercises: Array,
})


</script>







<template>
  <div id="exercise-list">
    <table>
      <thead>
        <tr>
          <th>Exercise Name</th>
          <th>Distance</th>
          <th>Calories Burned</th>
          <th>Time</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="exercise in exercises" :key="exercise.id">
        <td>{{ exercise.name }}</td>
        <td>{{ exercise.distance }}</td>
        <td>{{ exercise.calories }}</td>
        <td>{{ exercise.time }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>






<style scoped></style>
