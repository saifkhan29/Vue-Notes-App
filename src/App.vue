<template>
  <div>
       <!-- start of modal --> 
       <div class="overlay" @click="showModal = false" v-if="showModal">
        <div class="modal" @click.stop >
          <textarea v-model="newNote" name="note" id="note" cols="30" rows="10"></textarea>
          <div class="modal-btn-cont">
            <button class="modal-btn bubbly-button mt-4 me-2" @click="animateButton">Add Notes</button>
            <button class="modal-btn close-button mt-4" @click="showModal = false">Close</button>
          </div>
        </div>
       </div>
       <!-- end of modal -->
       <!-- start of notes body -->
      <div class="container py-5">
        <div class="row">
          <div class="col-12 my-2 heding-container d-flex justify-content-between">
            <h1>Notes</h1>
            <button @click="showModal = true" class="align-self-center notes-button">+</button>
          </div>
          <div class="col-12 mt-5 cards-container">
            <div class="card">
              <p class="card-content">Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium vero illum eius culpa, delectus corporis laboriosam error velit suscipit modwi!</p>
              <p class="date">04/07/2024</p>
            </div>
            <div class="card">
              <p class="card-content">Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium vero illum eius culpa, delectus corporis laboriosam error velit suscipit modwi!</p>
              <p class="date">04/07/2024</p>
            </div>
          </div>
        </div>
      </div>
      <!-- end of notes body -->
  </div>
</template>

<script setup>

import { ref } from "vue"

const showModal = ref(false)
const newNote = ref("")
const notes = ref([])

const addNote = () => {
}

const animateButton = (e) => {
  e.preventDefault();
  e.target.classList.remove('animate');
  e.target.classList.add('animate');
  setTimeout(() => {
    e.target.classList.remove('animate');
  }, 700);
};

</script>

<style scoped>
.notes-button{
  background: #000;
  color: #fff;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 20px;
  border: none;
  outline: none;  
  cursor: pointer;
  border: 2px solid #ffd500;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-bottom: 5px;
}

.notes-button:hover{
  border-color: #80ed99;
}

.card{
  width: 225px;
  height: 225px;
  background-color: #80ed99;
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between ;
  margin-right: 20px;
  margin-bottom: 20px;
}

.card-content{
  font-size: 14px;
}
.date{
  font-weight: bold;
  font-size: 12.5px;
}

.cards-container{
  display: flex;
  flex-wrap: wrap;
}

.overlay{
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.77);
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal{
  width: 750px;
  background-color: white;
  position: relative;
  border-radius: 10px;
  padding: 30px;
  display: flex;
  flex-direction: column;
  height: 400px;
  max-height: 100%;
}

.modal-btn{
  max-width: 150px;
}
</style>