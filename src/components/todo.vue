<template>
  <div class="container">
    <div> 
        <h1>Todo app </h1>
        <input type="text" class="todo-input" placeholder="whats new" v-model="newTodo" @keyup.enter="addtodo">
    </div>
    <ul v-for="(todo, index) in todos" :key="index">
        <div class="todoList" >
        <li> <h3> {{todo.title}} </h3> 
        <button v-on:click="removeTodo(index)"> remove </button> 
        </li>
        
        
        </div>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'todo',
  data () {
    return {
        newTodo: '',
        todos: [
            {
                id: 1,
                title:"clear the aws",
            },

            {
                id: 2,
                title:"wacth movie",
            },

            {
                id:3,
                title:" visit friend ",
            },
        ]
    }
    },
    methods:{
        addtodo(){
            this.todos.push({
                title: this.newTodo
            })
            this.newTodo="";
        },

        removeTodo(index){
            this.todos.splice(index, 1);
            this.newTodo="";

        }
    }
}
</script>


<style scoped>
*{
    box-sizing: border-box;
}
.container {
    position: relative;
    width: 30%;
    padding: 10px;
    background: grey;
    margin: 0 auto;
    border: 1px solid grey;
}
.todo-input {
    width: 60%;
    padding: 5px;
    border-radius: 4px;
    border: 1px solid grey;
    font-size: 15px;
    text-decoration: dotted;
}
.todoList>li {
    display: flex;
    position: relative;
}

.todoList>h3 {
    width: 20%;
    height: 30px;
}


li>button {
    border: 1px solid grey;
    position: absolute;
    height: 30px;
    margin-top: 14px;
    width: 30%;
    right: 10%;
    border-radius: 2px;
}
</style>
