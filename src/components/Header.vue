<template>
    <header>
        <input type="text" name="todoInput" v-model="todoValue" id="todoInput" placeholder="What are you going to do?">
        <button class="submit" v-on:click="createtodo(todoValue)">+</button>
    </header>
</template>

<script>
export default {
    name: "Header",
    methods: {
        createtodo: function (todoValue) {
            if (todoValue === "") return;
            this.$emit('createtodo', todoValue);
            this.todoValue = "";
        }
    },
    data() {
        return {
            todoValue: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    header {

        margin: 10%;
        display: flex;

        input {
            flex: 1;
            height: 50px;
            box-sizing: border-box;
            font-size: 20px;

            border-radius: 6px 0px 6px 0px;
            border-style: none;
            outline-style: none;
            background-color: rgba(255, 255, 255, 0.25);

            transition: 0.4s;

            &:hover {
                border-radius: 0px 6px 0px 6px;
                background-color: rgba(255, 255, 255, 0.5);
            }

        }

        .submit {
            margin-left: 5px;
            border-radius: 10%;
            outline-style: none;
            border-style: none;
            width: 50px;
            height: 50px;
            font-size: 28px;

            cursor: pointer;
        }
    }
    
</style>