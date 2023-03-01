<script setup>
import HelloWorld from './components/HelloWorld.vue'
import AddExercise from './components/AddExercise.vue'
import Run from './components/Run.vue'
import Walk from './components/Walk.vue'
import WeightLift from './components/WeightLift.vue'
import Swim from './components/Swimming.vue'
import ExerciseList from './components/ExerciseList.vue'


let exerciseOptions = {
  option1: 'Run',
  option2: 'Walk',
  option3: 'Weight Lift',
  option4: 'Swimming'
}

let exercises = [
  {
    id: 1,
    name: "Run1",
    distance: 3,
    calories: 100,
    time: 10.32
  },
  {
    id: 2,
    name: "Run2",
    distance: 3,
    calories: 100,
    time: 10.32
  },
  {
    id: 3,
    name: "Run3",
    distance: 3,
    calories: 100,
    time: 10.32
  }
]


function addExercise(exercise) {
    
  const lastId = exercises.length > 0 ? exercises[exercises.length - 1].id : 0
  const id = lastId +1

    const newExercise = {
      id,
      ...exercise
    }
  exercises = [...exercises, newExercise]


  console.log(exercises)
}


</script>

<template>
  <HelloWorld msg="Exercise Tracker"/>

  <AddExercise v-bind="exerciseOptions" />

  <exercise-list :exercises="exercises"/>

  <Run @add="addExercise"/>
  
  <Run msg="Track Your Run"/>
  <Walk msg="Track Your Walk"/>
  <WeightLift msg="Track Your Exercise"/>
  <Swim msg="Track Your Swim"/>

</template>

<style scoped>

</style>
