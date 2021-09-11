<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <my-element></my-element>
        </div>
        <script>
        Vue.component('my-element',{
            template: '<strong>My Component!!</strong>'
        })
        var app = new Vue({
            el: '#app',
        })
        </script>
    </body>
</html>