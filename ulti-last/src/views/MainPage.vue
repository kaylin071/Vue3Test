<template>
  <div class="grid-container">
    <div class="square">
      <router-link to="/Details" class="r">Employee Details </router-link>
    </div>
    <div class="square">
      <router-link to="/Home" class="r">Employee Logins</router-link>
    </div>
  </div>
</template>

<style>
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-row-gap: 50px;
  grid-column-gap: 10px;
  padding-left: 25%;
  padding-top: 5%;
  text-decoration: none;
}

.grid-container > div {
  background-color: rgba(255, 0, 0, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
  text-decoration: none;
}
.square {
  height: 250px;
  width: 250px;

  border-radius: 25px;
  text-decoration: none;
}
.r {
  text-decoration: none;
   color:white;

}
</style>
