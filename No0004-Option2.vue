<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="./CSS/style.css">
        <title>Option(DOM)</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <div class="collection">
                <h3>はじめに</h3>
                <span>ここの内容は<a href="https://www.tohoho-web.com/ex/vuejs.html">Vue.js入門 - とほほのＷＷＷ入門</a>に記述されているモノを写しているだけです。詳しく知りたい場合は自分で調べてね。<br>ここでは、オプション（DOM）についてをいろいろ試しているよ。</span>
            </div>

            <div class="collection">
                <h3>Data</h3>
                <div>{{ message1 }}</div>
                <div class="memo">Displayの最初に行っていたことのおさらいです。</div>
            </div>

        </div>
        <script>

        var app = new Vue({
            el: '#app',
            data: {
                message1: 'Hello world!!',
            },
            methods: {
            },
        });        
        </script>
    </body>
</html>