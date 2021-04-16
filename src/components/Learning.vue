<template>
    <div>
        <label for="goal">Goal</label>
        <input type="text" id="goal" v-model="entredval" />
        <button @click="addGoal">Add Goal</button>
      </div>
      <ul>
          <li :key="goal" v-for="goal in goals">{{ goal }}</li>
      </ul>
</template>
<style scoped>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}



label, input {
  margin-bottom: 0.5rem;
  display: block;
  width: 100%;
}
input{
  height: 30px;
}

label {
  font-weight: bold;
}

ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}

li {
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid #ccc;
}
</style>
<script>
export default {
  name: 'Learning',
  data() {
      return{
          goals: [],
          entredval:''
      }
  },
  methods: {
      addGoal(){
          if(this.entredval){
            this.goals.push(this.entredval);
            this.entredval = '';
          }
      }
  }
}
</script>