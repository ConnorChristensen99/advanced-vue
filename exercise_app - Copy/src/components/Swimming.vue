<script setup>

defineProps({
  msg: String,
})


function closeOptions() {
    let form = document.getElementById('swimForm')
    let options = document.getElementById('options')
    if (form.classList.contains('invisible')) {
        form.classList.remove('invisible')
    }else {
        form.classList.add('invisible')
    }

    options.classList.remove('invisible')
  }

</script>







<template>
    <div id="swimForm" class="invisible">

        <div id="header">
  <h3 class="openingTitle">{{ msg }}</h3>
  <i  @click="closeOptions" class="close">&#10006;</i>
</div>

<form>
  <label for="name">Name Swim:</label>
  <input type="text" id="name" name="name">
  <label for="date">Date:</label>
  <input type="date" id="date" name="exercise-date" value="2023-02-22" min="2023-01-01" max="2025-12-31">
  <label for="location">Location:</label>
  <input type="text" id="location" name="location">
  <label for="distance">Distance:</label>
  <input type="number" id="distance" name="distance" placeholder="laps/lengths">
  <label for="calories">Calories Burned:</label>
  <input type="text" id="calories" name="calories">
  <label for="runtime">Swim Time:</label>
  <input type="text" name="duration" id="durationForm" maxlength=8 pattern="^((\d+:)?\d+:)?\d*$" title="hh:mm:ss" placeholder="hh:mm:ss" size=30>
  <label for="notes">Notes:</label>
  <input type="textarea" id="notes" name="notes">
  
  <input class="submitForm" type="submit" value="Submit">
</form>

    </div>
</template>






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
#swimForm {
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
.submitForm {
    border: none;
    border-radius: 10px;
    margin-top: 20px;
}
.submitForm:hover {
    cursor: pointer;
    background-color:rgb(91, 83, 99)
}

</style>
