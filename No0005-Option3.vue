<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="./CSS/style.css">
        <title>Option(Life cycle/ Hook)</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <div class="collection">
                <h3>はじめに</h3>
                <span>ここの内容は<a href="https://www.tohoho-web.com/ex/vuejs.html">Vue.js入門 - とほほのＷＷＷ入門</a>に記述されているモノを写しているだけです。詳しく知りたい場合は自分で調べてね。<br>ここでは、オプション（その他いろいろ）についてをいろいろ試しているよ。</span>
            </div>

            <div class="collection">
                <h3>Life cycle/ Hook</h3>
                <div class="memo">
                ライフサイクル、イベントハンドラ、メモだけ残す。<br>
                beforeCreate	インスタンスが作成される直前に呼ばれます。<br>
                created	インスタンスが作成された直後に呼ばれます。<br>
                beforeMount	render によってマウントされる直前に呼ばれます。<br>
                mounted	render によってマウントされた直後に呼ばれます。<br>
                beforeUpdate	インスタンスのデータが更新される直前に呼ばれます。<br>
                updated	インスタンスのデータが更新された直後に呼ばれます。<br>
                activated	コンポーネントが活性化する時に呼ばれます。<br>
                deactivated	コンポーネントが非活性化する時に呼ばれます。<br>
                beforeDestroy	インスタンスが破棄される直前に呼ばれます。<br>
                destroyed	インスタンスが破棄された直後に呼ばれます。<br>
                errorCaptured	エラーがキャプチャされた時に呼ばれます。<br>
                </div>
            </div>

            <div class="collection">
                <h3>Directives</h3>
                <div v-myfont>Hello!!</div>
                <div class="memo">ディレクティブを自作できる。ここでは、フォントサイズを変えているだけだがイベントフックで各タイミング別に動作させられそう。</div>
            </div>

            <div class="collection">
                <h3>Filters</h3>
                <div>{{ message1 | toUpper }}</div>
                <div>{{ message1 | toLower }}</div>
                <div class="memo">もとの値からフィルタ掛けをする。カナのフィルタ掛けなどにも使えそう。</div>
            </div>

            <div class="collection">
                <h3>Components</h3>
                <my-comp1></my-comp1>
                <my-comp2></my-comp2>
                <my-comp3></my-comp3>
            </div>

        </div>
        <script>
        var MyComponent1 = { template: '<div style="color: red">Hello!!</div>' };
        var MyComponent2 = { template: '<div style="color: green">Hello!!</div>' };
        var MyComponent3 = { template: '<div style="color: blue">Hello!!</div>' };
        var app = new Vue({
            el: '#app',
            data: {
                message1: 'Hello!!',
            },
            methods: {},

            created: function () {
                console.log(this);
            },

            directives: {
                myfont: {
                    inserted: function (el) {
                        el.style.fontSize = '24pt';
                    },
                },
            },

            filters: {
                toUpper: function (value) {
                    return value.toUpperCase();
                },
                toLower: function (value) {
                    return value.toLowerCase();
                },
            },

            components: {
                'my-comp1': MyComponent1,
                'my-comp2': MyComponent2,
                'my-comp3': MyComponent3,
            }
        });
        </script>
    </body>
</html>