<template>
    <section id="todos">
        <div class="todo" v-for="(todo, key) in todos" :key="key">
            <label>
                <input type="checkbox" name="done" v-if="todo.done" checked>
                    <input type="checkbox" name="done" v-else>
                    <p style="text-decoration: line-through;" v-if="todo.done">{{ todo.name }}</p>
                    <p v-else>{{ todo.name }}</p>
            </label>
            <button class="todoTrash" v-on:click="deletetodo(todo)"><i class="fas fa-trash-alt"></i></button> 
        </div>
    </section>
</template>

<script>
export default {
    name: "Todos",
    props: ["todos"],
    methods: {
        deletetodo: function (todo) {
            this.$emit('deletetodo', todo.id);
        }
    }
}
</script>

<style lang="scss" scoped>

    .todo {
        display: flex;
        flex: 1;
        padding: 15px;
        background: white;
        font-size: 20px;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        border-radius: 5px;
        margin: 0 10% 2% 10%;
        justify-content: space-between;

        label p {
            display: inline;
            margin-left: 5px;
        }

        .todoTrash {
            background: transparent;
            outline-style: none;
            border-style: none;
            cursor: pointer;

            :hover {
                color: red;
                transition: 0.2s;
            }
        }
    }
</style>