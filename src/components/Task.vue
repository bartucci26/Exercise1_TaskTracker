<template>
<div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{task.text}}
        <div>
     <i @click="$emit('flag-task',task.id)" :class="[task.importance ? 'is-orange' : 'is-blue']" class="far fa-flag"></i>
     <i @click="$emit('delete-task',task.id)" class="fas fa-times"></i>
     
     </div>
    </h3>
    <p>{{task.day}}</p>
</div>
    
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object,

    },
   }
</script>

<style scope >
.fas {
    color: rgb(184, 73, 73);
    margin-left:8px
}
.is-blue {
    color: rgb(67, 124, 230);
}
.is-orange {
    color:orange;
}
.task {
    background: #f4f4f4;
    margin:5px;
    padding: 10px 20px;
    cursor: pointer;
}
.task.reminder {
    border-left: 5px solid green;
}
.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>