<script setup>
import HelloWorld from './components/HelloWorld.vue'
import AddExercise from './components/AddExercise.vue'
import Run from './components/Run.vue'
import Walk from './components/Walk.vue'
import WeightLift from './components/WeightLift.vue'
import Swim from './components/Swimming.vue'


let exerciseOptions = {
  option1: 'Run',
  option2: 'Walk',
  option3: 'Weight Lift',
  option4: 'Swimming'
}


</script>

<template>
  <HelloWorld msg="Exercise Tracker"/>

  <AddExercise v-bind="exerciseOptions"/>

  <Run msg="Track Your Run"/>
  <Walk msg="Track Your Walk"/>
  <WeightLift msg="Track Your Exercise"/>
  <Swim msg="Track Your Swim"/>

</template>

<style scoped>

</style>
