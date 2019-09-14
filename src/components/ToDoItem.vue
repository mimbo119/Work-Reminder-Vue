<template>
    <v-container>
        <v-layout text-center wrap>
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
    export default {
        name: 'todo-item',
    }
</script>

<style>
</style>