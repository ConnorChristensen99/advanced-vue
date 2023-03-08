<script setup>
import HelloWorld from './components/HelloWorld.vue'
import AddExercise from './components/AddExercise.vue'
import Run from './components/Run.vue'
import Walk from './components/Walk.vue'
import WeightLift from './components/WeightLift.vue'
import Swim from './components/Swimming.vue'
import ExerciseList from './components/ExerciseList.vue'
import PastExercises from './components/PastExercises.vue'
import Past from './components/PastExercises.vue'
</script>

<template>
  <HelloWorld msg="Exercise Tracker"/>

  <AddExercise v-bind="exerciseOptions"/>

  <exercise-list @past="addDeleted" @delete="deleteExercise" @edit="editExercise" :exercises="exercises"/>

  <PastExercises :pastExercises="pastExercises"/>



 <Run @add="addExercise"/>
 <Walk @add="addExercise"/>
 <WeightLift @add="addExercise"/>
 <Swim @add="addExercise"/>

</template>

<script>

export default{
  name: 'app',
  components: {
    ExerciseList,
    AddExercise,
    PastExercises
  },
  data() {
    return {
    exercises: [
  {
    id: 1,
    name: "Run in the Park",
    date: '3/3/23',
    distance: 3,
    calories: 1000,
    time: 10.32
  },
  {
    id: 2,
    name: "Swim at the Rec",
    date: '3/10/23',
    distance: 2,
    calories: 900,
    time: 10
  },
  {
    id: 3,
    name: "Walk with the dogs",
    date: '3/15/23',
    distance: 1,
    calories: 270,
    time: 12
  }
],
exerciseOptions: {
  option1: 'Walk',
  option2: 'Walk',
  option3: 'Weight Lift',
  option4: 'Swimming'
},
pastExercises: [
{
    id: 1,
    name: "Run in the Park",
    date: '3/3/23',
    distance: 3,
    calories: 1000,
    time: 10.32
  }
]
    }
  },
  methods: {
    addExercise(exercise) {
    const lastId = this.exercises.length > 0 ? this.exercises[this.exercises.length - 1].id : 0
    const id = lastId +1
  
      const newExercise = {
        id,
        ...exercise
      }

 
    this.exercises = [...this.exercises, newExercise]

  },
  deleteExercise(id) {
    this.exercises = this.exercises.filter(
      exercise => exercise.id !== id
    )
  },
  editExercise(id, updatedExercise) {
  exercises = exercises.map(exercise => {
    exercise.id === id
    ? updatedExercise
    : exercise
  })
},
addDeleted(exercise) {
  this.pastExercises = [...this.pastExercises, exercise]
}
  }
}



</script>

<style scoped>

</style>
