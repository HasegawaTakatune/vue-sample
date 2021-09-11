<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <input v-model="message">
            <div>Message:{{ message }}</div>
            <br>
            <div v-pre>Message: {{ message }}</div>
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {
                message: 'Hello world!',
                }
        })
        </script>
    </body>
</html>