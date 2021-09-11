<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="./CSS/style.css">
        <title>Global API</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <div class="collection">
                <h3>はじめに</h3>
                <span>ここの内容は<a href="https://www.tohoho-web.com/ex/vuejs.html">Vue.js入門 - とほほのＷＷＷ入門</a>に記述されているモノを写しているだけです。詳しく知りタイ場合は自分で調べてね。<br>ここでは、グローバルAPIの利用についてをいろいろ試しているよ。</span>
            </div>

            <div class="collection">
                <h3>Component1</h3>
                <my-component1></my-component1>
            </div>

            <div class="collection">
                <h3>Component2</h3>
                <my-component2></my-component2>
            </div>
        </div>
        <script>
        Vue.component('my-component1',{ template: '<strong>Hello!!</strong>' });
        var MyComponent2 = Vue.extend({ template: '<strong>Hello!!</strong>' });
        Vue.component('my-component2', MyComponent2);
        var app = new Vue({
            el: '#app',
        })
        </script>
    </body>
</html>