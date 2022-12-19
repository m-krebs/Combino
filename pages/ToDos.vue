<template>
  <h1>Your ToDos</h1>
  <ToDoList list=''/>
  <ToDoItem todoName='Jonas hauen'/>
  <ToDoItem todoName='Gin hauen'/>
  <ToDoItem todoName='Bug installieren'/>
</template>

<script>
import ToDoItem from '~/components/todos/ToDoItem.vue';
import ToDoList from '~/components/todos/ToDoList.vue';

export default {
  name: 'ToDo',
  components: {ToDoList, ToDoItem},
};
</script>

<style scoped>

</style>