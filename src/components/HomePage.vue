<template>
    <div id="home">
        <h5>{{  title  }}</h5>
        <hr>
        <h5>Conditionals and Loops</h5>
        <div id="app-3">
            <span v-if="seen">Now you see me [v-if]</span>
            <ol>
                <li v-for="(todo, id ) in todos1" :key="id">
                    {{  todo.text  }}
                </li>
            </ol>
        </div>
        <hr>
        <h5>Handling user input</h5>
        <p>v-on directive to attach event listeners that invoke methods on our Vue instances</p>
        <p>v-model directive that makes two-way binding between form input and app state</p>
        <p>{{  message  }}</p>
        <!-- Two-way data binding -->
        <input v-model="message">
        <!-- <button v-on:click="reverseMessage">Reverse Message</button> -->
        <button @click="reverseMessage">Reverse Message</button>

        <hr>
        <h5>Composing with components</h5>
        <p>an abstraction that allows us to build large-scale applications composed of small, self-contained, and often
            reusable components</p>
        <hr>
        <h5>Todo</h5>
        <div id="todo-list-example">
            <form v-on:submit.prevent="addNewTodo">
                <label for="new-todo">Add a todo</label>
                <input v-model="newTodoText" id="new-todo" placeholder="E.g. Feed the cat">
                <button>Add</button>
            </form>
            <!-- v-bind:title="todo.title" -->
            <ul>
                <li id="todo-item" v-for="(todo, index) in todos" v-bind:key="todo.id"
                    v-on:remove="todos.splice(index, 1)">{{  todo.title }}</li>
            </ul>
        </div>
        <hr>
        <ButtonCounter name="button1" />
        <ButtonCounter name="button2" />
       <SmallCard/>
        <hr>
        <!-- slots -->

        <FrameCard>
            <img src="../assets/images/logo.png" />
        </FrameCard>

        <ParentComp/>
        
    </div>
</template>

<script>
import ButtonCounter from "./ButtonCounter.vue";
import SmallCard from "./SmallCard.vue";
import FrameCard from "./FrameCard.vue";
import ParentComp from "./ParentComp.vue";

export default {
    name: "HomePage",
    props: {
        title: String,
    },
    methods: {
        reverseMessage: function () {
            this.message = this.message.split("").reverse().join("");
        },
        // Object.freeze(obj)
        addNewTodo: function () {
            this.todos.push({
                id: this.nextTodoId++,
                title: this.newTodoText
            });
            this.newTodoText = "";
        }
    },
    data() {
        return {
            at_created: 1,
            seen: true,
            message: "Hello Vue.js!",
            dateMessage: "You loaded this page on " + new Date().toLocaleString(),
            todos1: [
                { text: "Learn JavaScript", id: 1 },
                { text: "Learn Vue", id: 2 },
                { text: "Build something awesome", id: 3 }
            ],
            obj: {
                foo: "bar"
            },
            newTodoText: "",
            todos: [
                {
                    id: 1,
                    title: "Do the dishes",
                },
                {
                    id: 2,
                    title: "Take out the trash",
                },
                {
                    id: 3,
                    title: "Mow the lawn"
                }
            ],
            nextTodoId: 4,
            artists: [
                { id: 1, name: 'Stormzy', genre: 'hiphop', country: 'United Kingdom' },
                { id: 2, name: 'Burna Boy', genre: 'afrobeats', country: 'Nigeria' },
                { id: 3, name: 'Davido', genre: 'afrobeats', country: 'Nigeria' },
                { id: 4, name: 'Sarkodie', genre: 'hiphop', country: 'Ghana' },
            ],
        };
    },
    created: function () {
        // `this` points to the vm instance
        console.log("Lifecycle => at_created var is: " + this.at_created);
    },
    components: { ButtonCounter, SmallCard, FrameCard, ParentComp }
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/style.scss';
</style>