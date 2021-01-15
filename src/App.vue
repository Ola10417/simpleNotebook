<template>
  <div id="app">
    <h1>Dodaj nową notatkę</h1>
    <div>
      <addNewItem :newItem="newItem" @addItem="addNewItem" />
    </div>
    <div>
      <showItems :note="note" v-for="note in notes" :key="note.id" @deleteItem="delItem" />
    </div>
  </div>
</template>

<script>
import showItems from './components/showItems.vue';
import addNewItem from './components/addNewItem.vue';
export default {
  components: {
        showItems,
        addNewItem
    },
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
    addNewItem(title, body){
      var today = new Date();
      var dd = String(today.getDate()).padStart(2, '0');
      var mm = String(today.getMonth() + 1).padStart(2, '0'); 
      var yyyy = today.getFullYear();
      today = dd + '.' + mm + '.' + yyyy;
      this.notes.push({id:Math.random(), title:title, body:body, date:today})
      this.newItem={title:'', body:''}
    },

    delItem(note){
      console.log(note);
      this.notes.splice(this.notes.indexOf(note),1);
    },

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
