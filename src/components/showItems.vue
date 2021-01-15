<template>
    <div class="note" >
        <div class="close" @click="deleteItem"><i class="far fa-times-circle closeicon" ></i></div>
       <h2>{{note.title}}</h2>
        <h4>{{note.body}}</h4>
        <h5>{{note.date}}</h5> 
    </div>
</template>

<script>
    export default {
        props: [
        'note'
        ],
        methods: {
            deleteItem(){
                this.$emit('deleteItem', this.note);
                
            }
        }
    }
</script>
<style>
.note 
{
 position: relative;
 background-color: rgb(247, 235, 134);
 margin: auto;
  width: 50%;
  padding-top:10px;
  margin-top:15px;
  padding-bottom:10px;
}

.close{
    position: absolute;
    right:0;
    top: 0;
}

.closeicon{
font-size:28px;
margin-right: -10px;
margin-top:-5px;
}
.closeicon:hover{
    cursor: pointer;
    color: rgb(204, 47, 47);
}

</style>