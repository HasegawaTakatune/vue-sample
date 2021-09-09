<!DOCTYPE html>
<html lang="ja">
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>

    <div id="app">
        <div class="outLine">{{ message }}</div>
        <div v-text="message" class="outLine"></div>
        <div v-html="message" class="outLine"></div>
    </div>
    <script>
    var app = new Vue({
        el: '#app',
        data: {message: '<br>Hello! <br><br>'}
    })
    </script>
    <style>
    #app .outLine{
        border:solid thin GREEN;
        width: 200px;
        height: auto;
    }
    </style>
    </body>
</html>