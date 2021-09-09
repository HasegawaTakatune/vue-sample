<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <div>
                <input type="radio" name="type" onclick="app.type='A'" checked>A
                <input type="radio" name="type" onclick="app.type='B'">B
                <input type="radio" name="type" onclick="app.type='C'">C
            </div>

            <div>
                <span v-if="type == 'A'">Good morning.</span>
                <span v-else-if="type == 'B'">Hello!</span>
                <span v-else="type == 'C'">Bye!</span>
            </div>
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {type: 'A'}
        })
        </script>
    </body>
</html>