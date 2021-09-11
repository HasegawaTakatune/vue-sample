<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <button v-on:click="hello">Hello</button>
            <button @click="hello">Hello</button>

            <input type="button" v-bind:value="label" @click="hello">
            <input type="button" :value="label" @click="hello">
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {label: 'Hello!'},
            methods:{hello:function() {
                alert("Hello!");
            }}
        })
        </script>
    </body>
</html>