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
  <transition name="fade">
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
  </transition>
</section>

<section>
  <transition name="fade">
  <div class="menu" v-show="menu">
  <button @click="menu = !menu" class="btn close close2">X</button>
  <img src="./assets/Menu-Oct-2021.jpg" alt="menu" class="menu-img" />
  </div>
  </transition>
</section>
<section>
   <transition name="fade">
  <div class="about" v-show="about">
  <button @click="about = !about" class="btn close">X</button>
  <img src="./assets/res.jpg" alt="chef" class="about-img" />
  <h3 class="about-title">Open Friday, Saturday & Sunday <br> Hours 2pm-10pm</h3>
  
  <div class="people">
    <div class="person">
  <img class="about-face" src="./assets/111.jpg" alt="face pic">
 <h5 class="about-name"> Frank Sabotianos</h5>
 <h6 class="about-name-title">Head Chef</h6>
 </div>
 <div class="person">
  <img class="about-face" src="./assets/112.jpg" alt="face pic">
 <h5 class="about-name"> Nina Cocisita</h5>
 <h6 class="about-name-title">Owner</h6>
 </div>
 
 </div>
  <div class="about-info">
    On top of our exquisite steakhouse menu, aims for an ambiance that will make for a memorable fine-dining experience from the moment you pull up to the moment you leave.

The luxurious Scottsdale fine-dining experience at Steakhouse begins before you even enter the restaurant.
  </div>
 </div>
 </transition>
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

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

 
.btn {
  background-color: #ffae2c70;
  color: #ffffff;
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
    box-shadow: #ffffff -5px 5px 30px, #ffae2ca8 -10px 10px 10px;

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
    box-shadow: #ffffff -5px 5px 30px, #ffae2ca8 -10px 10px 10px;

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
  /* min-width: fit-content; */
  height: auto;
  /* object-fit: cover; */
  position: absolute;
  top: -100%;
  left: 0;
  z-index: -1;

  }
  .info {
display: none;
 margin-left: 10%;
  }
.res, .menu, .about {
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
  height: 90%;
  border-radius: 5%;
  box-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
}
.about {
  height: 90%;
}
.res-title {
   font-family: 'Yellowtail', cursive;
  margin-top: -5%;
  font-size: 5rem;
  text-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
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
  top: -45%;
  right: 3%;
  font-size: 4rem;
  font-weight: bold;
  color: #000000;
  cursor: pointer;
  border-radius: 50%;
}
.close2 {
  display: grid;
  place-items: center;
  top: -45%;
  right: 2%;
  background-color: #ffffff;
  font-size: 7rem;
  padding: 0px;
  border-radius: 0;
  width: 130px;
  height: 110px;
}
.menu-img {
  width: 100%;
  height: 100%;
  object-fit: fill;
  
}
.about {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: auto;
}
.about-img {
  margin: auto;
  width: 400px;
  opacity: 0.9;
  object-fit: fill;
  border-radius: 20%;
    box-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;

}
.about-face {
  width: 200px;
  object-fit: fill;
  border-radius: 50%;
  opacity: 0.9;
  box-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
  margin-top: 20%;
}
.about-title {
  color: #000000;
  font-size: 3rem;
  font-weight: bold;
  margin-top: -5%;
  text-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
  margin: auto;
}
.about-info {
  color: #000000;
  font-weight: bold;
  font-size: 2rem;
  text-shadow: #ffffff -1px 1px 5px, #ffae2ca8 -10px 10px 10px;
  margin: 6%;
}
.people {
  display: flex;
  flex-direction: row;
  align-items: space-evenly;
  justify-content: space-evenly;
  margin: auto;
  margin-top: -5%;
}
.person {
  display: flex;
  flex-direction: column;
  align-items: space-evenly;
  justify-content: space-evenly;
  margin-left: 15%;
  margin-right: 15%;
}
.about-name {
  color: #000000;
  font-size: 2.5rem;
  font-weight: bold;
  margin-top: -5%;
  text-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
  margin: auto;
}
.about-name-title{
  color: #000000;
  font-size: 2rem;
  font-weight: bold;
  margin-top: -5%;
  text-shadow: #ffffff -10px 10px 30px, #ffae2ca8 -10px 10px 10px;
  margin: auto;
}
@media (max-width: 1700px) {
  .main-cont {
    width: 100%;
   display: flexbox;
   flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    }
  .hero {
 min-height: 100%;
 min-width: 1024px;
 width: 100%;
 height: auto;
 position: fixed;
 top: 0;
 left: 0;
 left: 50%;
 margin-left: -512px;
  }
  .btn-cont {
    position: sticky;
    margin-top: 70%;
    left: 47%;
    margin-left: -15%;
    width: 30%;
    height: 100%;

    z-index: 1;
  }
  .btn {
    font-size: 0.8rem;
  }
  .about, .menu, .res {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    /* justify-content: center;
    margin-left: 20%;
    margin-top: 35%; */
    z-index: 2;
  }
  .menu-img {
    object-fit: contain;
  }
  .title {
    font-size: 4rem;
  }
  .close {
    margin-top: 105%;
  }
  .close2 {
    font-size: 2rem;
    width: 50px;
    height: 50px;
  }
  .about-face {
    width: 100px;
  box-shadow: none;
  }
  .about-name, .about-name-title {
    font-size: 1.5rem;

  }
  .about-title {
    font-size: 1.7rem;
  }
  .about-img {
    width: 200px;
  }
  .about-info {
    font-size: 1.5rem;
  }
}

</style>
