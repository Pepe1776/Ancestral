<script setup lang="ts">
import { ref } from 'vue';
  const menu = ref(false);
  const res = ref(false);
  const about = ref(false);

  const form = ref();
  const name = ref();
  const date = ref();
  const time = ref();
  const guest = ref();
  const special = ref();
  const onSubmit = () => {
    console.log(name.value);
  };
</script>


<template class="temp">
<div class="main-cont">
<section class="sec1">
    <div class="hero-wrapper">
      <img class="hero" alt="Steak pic" src="./assets/hall.jpg" />
    </div>
  <h1 class="title">Ancestral</h1>
  <h3 class="phone">(623)755-2366</h3>
    <h2 class="sub-title">Animal based menu with the most <br> nutrient rich foods on the planet</h2>
<!-- <img class="svg" src="./assets/steak.svg" alt="steak icon"> -->
</section>

<section>
  <div class="btn-cont">
  <button @click="res = !res" class="btn">Reservations</button>
  <button @click="menu = !menu" class="btn">Menu</button>
  <button @click="about = !about" class="btn">About_Us</button>
  </div>
</section>
<section>
  <div class="res" v-show="res">
  <h3 class="res-title">Reservations</h3><button @click="res = !res" class="btn close">X</button>
  <form class="form" @submit="onSubmit">
  <input v-model="name" name="name" type="text" placeholder="Name" />
  <input v-model="guest" name="guest" type="number" placeholder="number of guest" />
  <input v-model="date" name="date" type="date" />
  <input v-model="time" name="time" type="time" />
  <input v-model="special" name="special" type="text" placeholder="special request" />
  <buttton class="btn2" value="Save Information" @click="onSubmit()" type="submit">Submit</buttton>
  </form>
  </div>
</section>
</div>
</template>

<style>
#app {
font-family: 'Zen Loop', cursive;  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
.btn {
  background-color: #ffae2c70;
  color: #000000;
  border: 1px solid #000000;
  padding: 10px;
  margin-top: 40%;
  margin-left: 30%;
  width: min-content;
  height: min-content;
  line-height: 1;
  font-size: 2rem;
  font-weight: bold;
  border-radius: 5%;
  transition: all 0.3s ease-in-out;
}
.btn2 {
  background-color: #f6f6f670;
  color: #000000;
  border: 1px solid #000000;
  padding: 10px;
  margin-top: 15%;
  width: min-content;
  height: min-content;
  line-height: 1;
  font-size: 2rem;
  font-weight: bold;
  border-radius: 5%;
  transition: all 0.3s ease-in-out;
}
.btn:hover, .btn:focus, .btn:active, .btn2:hover, .btn2:focus, .btn2:active {
  background-color: #ffae2c;
  border: 1px solid #ffffff;
  color: #000000;
  transform: scale(1.1);
}

.main-cont {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
 
}
.btn-cont {
  display: flex;
  flex: 1, 0;
  align-items: space-evenly;
  justify-content: space-evenly;
  width: 100%;
  margin-top: -100%;
  margin-left: 200%;
}

.svg {
drop-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
    text-shadow: #000000 0 0 30px, #fd0000 0 0 10px;
  width: 100%;
  max-width: 200px;
  left: 6%;
  position: absolute;
 
}
.title {
 margin: auto;
 margin-left: 10%;
  text-shadow: #ffae2c 0 0 30px, #000000 0 0 10px;
  font-size: 7rem;
  font-weight: bold;
  font-family: 'Yellowtail', cursive;
 
 
}
.sub-title {
  margin-top: -7%;
  margin-left: 23%;
  text-shadow: #ffae2c 0 0 30px, #fd0000 0 0 10px;
  font-size: 2rem;
  font-weight: bold;
    
}
.phone {
  color: #ffae2c;
  font-size: 2rem;
  margin-top: -19px;
  margin-left: 25%;
    text-shadow: #000000 0 0 30px, #fd0000 0 0 10px;

}
.hero {
  display: flex;
  flex: 1, 0;
  width: 100%;
  min-width: fit-content;
  height: auto;
  object-fit: cover;
  position: absolute;
  top: -100%;
  left: 0;
  z-index: -1;

  }
  .info {
display: none;
 margin-left: 10%;
  }
.res {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #ffae2ca8;
  width: 50%;
  height: 70%;
  border-radius: 5%;
}
.res-title {
  margin-top: -5%;
  font-size: 5rem;
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: -5%;
}

input {
  width: 100%;
  height: 40px;
  border: 1px solid #000000;
  border-radius: 5px;
  padding: 10px;
  margin-top: 10px;
  font-size: 1.5rem;
  font-weight: bold;
}
.close {
  position: absolute;
  top: -80%;
  right: 3%;
  font-size: 2rem;
  font-weight: bold;
  color: #000000;
  cursor: pointer;
}
</style>
