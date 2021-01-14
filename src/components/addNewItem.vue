<template>
<div>
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
        }
    }
}
</script>