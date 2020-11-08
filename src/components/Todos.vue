<template>
    <section id="todos">
        <div class="todo" v-for="(todo, key) in todos" :key="key">
            <input type="checkbox" name="done" v-if="todo.done" checked>
            <input type="checkbox" name="done" v-else>
            <label for="do">
                {{ todo.name }}
            </label>
            <button class="todoTrash" v-on:click="() => deletetodo(todo.id)"><i class="fas fa-trash-alt"></i></button> 
        </div>
    </section>
</template>

<script>
export default {
    name: "Todos",
    props: ["todos"],
    methods: {
        deletetodo: function (id) {
            this.$emit('deletetodo', id);
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

        input:checked + label {
            text-decoration: line-through;
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