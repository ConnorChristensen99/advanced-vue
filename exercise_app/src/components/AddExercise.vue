<script setup>
defineProps({
  option1: String,
  option2: String,
  option3: String,
  option4: String
})

function closeOptions() {
    let options = document.getElementById('options')
    if (options.classList.contains('invisible')) {
    options.classList.remove('invisible')
    }else {
        options.classList.add('invisible')
    }
  }

  function findID(event) {
    let target = event.target
    
    let forwardLocation = target.id

    closeOptions()

    if(forwardLocation == 'option1') {
        let form = document.getElementById('runForm')
        form.classList.remove('invisible')
    }else if (forwardLocation == 'option2') {
        let form = document.getElementById('walkForm')
        form.classList.remove('invisible')
    }else if (forwardLocation == 'option3') {
        let form = document.getElementById('weightForm')
        form.classList.remove('invisible')
    }else if(forwardLocation == 'option4') {
        let form = document.getElementById('swimForm')
        form.classList.remove('invisible')
    }
  }

</script>

<template>
    <ul id="options" class="choose-exercise invisible">
        <div id="optionsScreen">
        <i @click="closeOptions" class="close">&#10006;</i>
        <li><button id="option1" @click="findID">{{ option1 }}</button></li>
        <li><button id="option2" @click="findID">{{ option2 }}</button></li>
        <li><button id="option3" @click="findID">{{ option3 }}</button></li>
        <li><button id="option4" @click="findID">{{ option4 }}</button></li>
    </div>
    </ul>
</template>

<style scoped>
.choose-exercise li {
    padding: 2%;
    color: black;
    
}
#optionsScreen {
    background-color: rgb(100,100,100,.9);
    display: flex;
    flex-direction: column;
    padding: 10%;
}
#optionsScreen i{
    color: black;
    font-size: xx-large;
    align-self: flex-end;
    padding-right: 5%;
    padding-bottom: 5%;
    margin-top: -40px;
}
#optionsScreen i:hover{
    cursor: pointer;
    color: white;
}
.choose-exercise button {
    padding: 2% 8% 2% 8%;
    width: 100%;
}
.choose-exercise button:hover {
    background-color: rgb(91, 83, 99);
    color: black;
}
.choose-exercise {
    list-style-type: none;
    position: fixed;
    left: 25%;
    right:0; 
    top: 25%;
    bottom: 0;
    overflow: auto;
    z-index: 9999;
}
#options {
    max-width: 800px;
}
</style>
