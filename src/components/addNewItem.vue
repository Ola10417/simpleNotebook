<template>
<div id="addnew">
    <input type="text" placeholder="Tytuł notatki" v-model="newItem.title"><br>
    <textarea rows="4" cols="50" placeholder="Napisz coś..." v-model="newItem.body"></textarea><br>
    <button @click="addItem()">Zapisz</button>
</div>
</template>
<script>
export default {
    props:[
        'newItem'
    ],
    methods:{
        addItem(){
            this.$emit('addItem', this.newItem.title, this.newItem.body);
        },
        
    }
}
</script>
<style>
#addnew{
    margin: auto;
    width: 50%;
    margin-bottom: 40px;
    padding-bottom: 20px;
    padding-top: 20px;
    background-color: rgb(247, 235, 134);
    border: 1px solid rgb(223, 209, 88);
}
input[type="text"]
{
    text-align: center;
    font-size: 24px;
    background: transparent;
    border-bottom: 2px solid rgb(194, 167, 46);
    border-top: none;
    border-right: none;
    border-left: none;
    margin-bottom: 25px;
}
textarea
{
    background: transparent;
    border: none;
    text-align: center;
    font-size: 16px;
}
button
{
    background-color:rgb(194, 168, 53);
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
</style>