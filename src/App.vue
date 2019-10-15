<template>
    <div class="todo-container">
    <div class="todo-wrap">
        <TodoHeader :addTodo='addTodo'/>
        <TodoList :todos='todos' :deleteTodo='deleteTodo'/>
        <TodoFooter/>  
    </div>
  </div>
</template>

<script>
    import TodoHeader from './components/TodoHeader'
    import TodoFooter from './components/TodoFooter'
    import TodoList from './components/TodoList'

    export default {
        data(){
            return {
                todos:[
                    {title:'吃饭',complete:false},
                    {title:'睡觉',complete:false},
                    {title:'亲佳佳',complete:true},
                ]
            }
        },
        methods:{
            addTodo(todo){
                this.todos.unshift(todo)
            },
            deleteTodo(index){
                this.todos.splice(index,1)
            }
        },
        components:{
            TodoHeader,TodoFooter,TodoList 
        }
    }
</script>

<style>
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>