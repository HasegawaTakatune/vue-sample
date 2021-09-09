<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <input type="checkbox" @click="change" checked>
            <span v-show="show">Hello!<span>
        </div>
        <script>
        var app = new Vue({
            el: '#app',
            data: {show: true},
            methods:{
                change: function(event) {
                    this.show = event.target.checked;
                }
            },
        })
        </script>
    </body>
</html>