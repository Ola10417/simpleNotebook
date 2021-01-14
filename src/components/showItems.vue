<template>
    <div>
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
    }
</script>