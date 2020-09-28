<template>
  <div>
    <form @submit.prevent="addTodo">
      <input type="text" name="title" placeholder="Add Todo.." v-model="title"/>
      <input class="btn" type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
        title: ''
    }
  },
  methods:{
      addTodo(){
        //   console.log(1);
        // e.preventDefault();
        
        const newTodo = {
            // id: uuid,
            title: this.title,
            completed: false
        }
        // send up to parent
        this.$emit('add-todo', newTodo);

        this.title = '';
      }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
submit[type="submit"] {
  flex: 2;
}
</style>
