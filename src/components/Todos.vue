<template>
    <section id="todos">
        <div class="todo" v-for="(todo, key) in todos" :key="key">
            <div class="job">
                <input type="checkbox" name="done">
                {{ todo.name }}</div>
        </div>
    </section>
</template>

<script>
export default {
    name: "Todos",
    props: ["todos"]
}
</script>

<style lang="scss" scoped>

    .todo {
        display: flex;
        flex: 1;
        margin: 15px;
        padding: 15px;
        background: white;
        font-size: 20px;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        border-radius: 5px;

        
    }
</style>