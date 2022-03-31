<script>
export default{
  name: 'App',
  data() {
    return {
      firstName:"Uttam",
      lastName : "kumar",
      email: 'uttampal.kumar1996@gmail.com',
      gender: 'male',
      picture:'uttam.jpg'
    }
  },
  methods:{
    async getUser(){

      const res = await fetch('https://randomuser.me/api')
      const { results } = await res.json() 
    
      this.firstName = results[0].name.fisrt,
      this.lastName = results[0].name.last,
      this.email = results[0].email,
      this.picture = results[0].picture.large,
      this.gender = results[0].gender


    }
  }

}

</script>

<template>
<div class="container">
 <img :src='picture' width="150" :class='gender' :alt="`${firstName} ${lastName}`" />
       <h1>{{firstName}} {{lastName}}</h1>
      <h3>Email: {{email}}</h3>
      <button :class='gender' @click='getUser'>Get Random User</button>
 
</div>
 
</template>

<style>
/* @import './assets/base.css'; */

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}
 

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  min-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 400px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html,
body {
  font-family: Arial, Helvetica, sans-serif;
}

#app {
  width: 400px;
  height: 100vh;
  margin: auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1,
h3 {
  margin-bottom: 1rem;
  font-weight: normal;
}

img {
  border-radius: 100%;
  border: 5px #333 solid;
  margin-bottom: 1rem;
  height: 150px;
  width: 150px;
}

.male {
  border-color: steelblue;
  background-color: rgb(70, 131, 180);
}

.female {
  border-color: pink;
  background-color: pink;
  color: #333;
}

button {
  cursor: pointer;
  display: inline-block;
  background: #333;
  color: white;
  font-size: 18px;
  border: 0;
  padding: 1rem 1.5rem;
}

button:focus {
  outline: none;
}

button:hover {
  transform: scale(0.98);
}


</style>
