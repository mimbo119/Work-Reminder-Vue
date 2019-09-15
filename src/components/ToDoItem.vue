<template>
    <v-container>
        <v-layout text-center wrap>
            <v-flex>
                    <span>...............</span>
            </v-flex>
        </v-layout>
        <div class="todo-items">
            <div class="items">{{todo.title}}</div>
            <div class="remove-items" @click="remove(index)"> &times;</div>
        </div>
    </v-container>
</template>

<script>
    export default {
        name: 'to-do-item',
        props:{
            todo:{
                type: Object,
                required: true,
            },
            index:{
                type:Number,
                required: true,
            }
        },

        data(){
            return{
                'id': this.todo.id,
                'title': this.todo.title
            }
        },

        methods:{
            remove(index){
                this.$emit('removedTodo', index)
            }
        }

    }
</script>

<style>
</style>