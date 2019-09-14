<template>
    <v-container class="container">
        <v-layout text-center wrap>
            <v-flex xs12>
                <v-img :src="require('../assets/logo.svg')" class="my-3" contain height="100"></v-img>
            </v-flex>
            <v-flex xs12 mb-5>
                <v-container>
                    <v-text-field label="To Do" placeholder="Add your todo" outlined v-model="newTodo" @keyup.enter="add()"></v-text-field>
                </v-container>
            </v-flex>
            <v-flex>
                <v-toolbar-title class="headline text-uppercase">
                    <span>Todos</span>
                </v-toolbar-title>
            </v-flex>
        </v-layout>
        <div v-for="todo in todos" :key="todo.id" class="todo-items">
            <div class="items">{{todo.title}}</div>
            <div class="remove-items" @click="remove(index)"> &times;</div>
        </div>
    </v-container>
</template>

<script>
    import ToDoItem from './ToDoItem'

    export default {
        name: 'todo',
        components: {
            ToDoItem
        },

        idTodo: 2,
        data() {
            return {
                newTodo: '',
                todos: []
            }
        },

        methods: {

            add() {

                if (this.newTodo.trim().length == 0) {
                    return
                }
                this.todos.push({
                    id: this.idTodo,
                    title: this.newTodo

                })

                this.newTodo = '',
                    this.idTodo++
            },

            remove(index){
                this.todos.splice(index, 1)
            }

        }

    };
</script>
<style>
    .todo-items {
        margin: 12px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        
        
    }
    .todo-items:hover{
        background-color: #cce6ff;
        border-radius: 20px;
    }
    .items{
        margin-left: 12px
    }

    .remove-items {
        cursor: pointer;
        margin: 8px;

    }
    .container{
        max-width: 600px !important;
    }
</style>