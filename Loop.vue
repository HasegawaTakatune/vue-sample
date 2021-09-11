<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <ul>
                <li v-for="color in colors">{{ color }}</li>
            </ul>
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {colors: ['Red', 'Green', 'Bule']}
        })
        </script>
    </body>
</html>