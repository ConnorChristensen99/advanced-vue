<template>
    <div id="runForm" class="invisible">

        <div id="header">
  <h3>Track Your Run</h3>
  <i @click="closeOptions" class="close">&#10006;</i>
</div>

<div id="exercise-form">
<form @submit.prevent>
  <label for="name">Name Run:</label>
  <input v-model="exercise.name" type="text" id="name" name="name">
  <label for="date">Date:</label>
  <input v-model="exercise.date" type="text" id="date" name="exercise-date" placeholder="mm/dd/yyyy">
  <label for="distance">Distance:</label>
  <input  v-model="exercise.distance" type="number" id="distance" name="distance" placeholder="Miles">
  <label for="calories">Calories Burned:</label>
  <input  v-model="exercise.calories" type="text" id="calories" name="calories">
  <label for="runtime">Run Time:</label>
  <input  v-model="exercise.time" type="text" name="duration" d="durationForm" maxlength=8 size=30 placeholder="mm:ss">
  
  <button @click="closeOptions(), handleSubmit()">Submit Exercise</button>
</form>
</div>

    </div>
</template>

<script>
let date
let distance
let calories
let time
export default {
    name: 'exercise-form',
    data() {
        return{
            exercise: {
            name: '',
            date,
            distance,
            calories,
            time
        },
    }
},
methods: {
    closeOptions() {
    let form = document.getElementById('runForm')
    let options = document.getElementById('options')
    if (form.classList.contains('invisible')) {
        form.classList.remove('invisible')
    }else {
        form.classList.add('invisible')
    }

    options.classList.add('invisible')
  },
  handleSubmit() {
    this.$emit('add', this.exercise)
  }
}
}

</script>






<style scoped>
#header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
#header i{
    font-size: xx-large;
    align-self: flex-end;
    padding-right: 5%;
    padding-bottom: 5%;
    margin-top: -40px;
}
#header i:hover{
    cursor: pointer;
    color: black;
}
.openingTitle {
    font-size: x-large;
    margin: none;
}
#runForm {
    background-color: rgb(136, 136, 136);
    padding: 2% 5% 2% 8%;
    list-style-type: none;
    position: fixed;
    left: 25%;
    right:25%; 
    top: 5%;
    bottom: 25%;
    overflow: auto;
    z-index: 9999;
    height: 80%;
}
form {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
form input {
    width: 50%;
    padding: 2%;
}
form label {
    padding-top: 3%;
}
button {
    border: none;
    border-radius: 10px;
    margin-top: 20px;
}
button:hover {
    cursor: pointer;
    background-color:rgb(91, 83, 99)
}

</style>
