<template>
  <div id="app">
    <div>
      <input type="text" placeholder="Tytuł notatki" v-model="newItem.title"><br>
      <textarea rows="4" cols="50" placeholder="Napisz coś..." v-model="newItem.body"></textarea><br>
      <button @click="addNewItem()">Zapisz</button>
    </div>
    <div>
      <div v-for="note in notes" :key="note.id" >
        <h2>{{note.title}}</h2>
        <h4>{{note.body}}</h4>
        <h5>{{note.date}}</h5>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      newItem:{title:'', body:''},
      notes: [
        {id:1,title:'rybki', body:'Pamietaj by nakarmic rybki!', date:'14.01.2021'},
        {id:2,title:'zakupy', body:'Zrob zakupy', date:'14.01.2021'},
      ]
    }
  },
  methods: {
    addNewItem(){
      var today = new Date();
      var dd = String(today.getDate()).padStart(2, '0');
      var mm = String(today.getMonth() + 1).padStart(2, '0'); 
      var yyyy = today.getFullYear();

      today = dd + '.' + mm + '.' + yyyy;
      this.notes.push({id:Math.random(), title:this.newItem.title, body:this.newItem.body, date:today})
      this.newItem={title:'', body:''}
    }

  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
