<template>
    <div id="pastexercises-list">
        <h3>Past Exercises</h3>
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
          <tr v-for="exercise in pastExercises" :key="exercise.id">
          <td>{{ exercise.name }}</td>
          <td>{{ exercise.date }}</td>
          <td>{{ exercise.distance }}</td>
          <td>{{ exercise.calories }}</td>
          <td>{{ exercise.time }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    name: 'pastexercises-list',
    props: {
      pastExercises: Array,
    },
    methods: {
    }
  }
  </script>
  
  
  
  
  
  
  <style scoped>
  h3 {
    margin-top: 10%;
  }
  th, td {
  border: 1px solid;
  padding: 15px;
  color: black;
  width: 100%;
}
table {
  margin-top: 35px;
  background-color: rgb(220, 230, 178);
  border-radius: 5px;
  padding: 15px;
}
  </style>