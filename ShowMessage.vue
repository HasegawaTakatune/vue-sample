<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <button onclick="location.reload()">再表示</button>
            <div>Message:<span v-cloak>{{ message }}</span></div>
            <div>Message:<span>{{ message }}</span></div>
            <br>
            <input type="text" v-model="message">
            <div>Message: <span v-once>{{ message }}</span></div>
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {message: 'Hello world!'}
        })
        </script>
        <style>
        [v-cloak]{display: none}
        </style>
    </body>
</html>