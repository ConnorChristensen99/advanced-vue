<script setup>

defineProps({
  msg: String,
})

function showOptions() {
  let options = document.getElementById('options')
  
  if (options.classList.contains('invisible')) {
    options.classList.remove('invisible')
  }
}
</script>







<template>
  <h1 class="openingTitle">{{ msg }}</h1>
  <button @click="showOptions">Add a New Exercise</button>
</template>






<style scoped>
</style>


