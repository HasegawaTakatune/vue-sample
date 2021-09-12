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
                <span>ここの内容は<a href="https://www.tohoho-web.com/ex/vuejs.html">Vue.js入門 - とほほのＷＷＷ入門</a>に記述されているモノを写しているだけです。詳しく知りたい場合は自分で調べてね。<br>ここでは、グローバルAPIの利用についてをいろいろ試しているよ。</span>
            </div>

            <div class="collection">
                <h3>Component1</h3>
                <my-component1></my-component1>
            </div>

            <div class="collection">
                <h3>Component2</h3>
                <my-component2></my-component2>
            </div>

            <div class="collection">
                <h3>Component next tick</h3>
                <button onclick="location.reload()">再表示</button>
                <div v-once>Default :{{ message1 }}</div>
                <div>nextTick callback :{{ message1 }}</div>
                <div class="memo">nextTickはDOM更新サイクル終了後に呼び出されるため。デフォルト値とコールバック値を確認するか、検証画面のコンソールからnextTickのbefore/afterを比較して確認を行う。</div>
            </div>

            <div class="collection">
                <h3>Vue set/delete</h3>
                <input type="button" @click="addColor" value="Add">
                <input type="button" @click="deleteColor" value="Delete">
                <ul>
                    <li v-for="(value, key) in colors">{{ key }}:{{ value }}</li>
                </ul>
            </div>

            <div class="collection">
                <h3>Vue directive</h3>
                <div v-myfont>Hello!!</div>
            </div>

            <div class="collection">
                <h3>Vue filter</h3>
                <div>{{ message2 | toupper }}</div>
            </div>

            <div class="collection">
                <h3>Vue use</h3>
                <div class="memo">自作のプラグインを呼び出せる。</div>
            </div>

            <div class="collection">
                <h3>Global mixin</h3>
                <div class="memo">グローバルミックスイン、後で詳しく確認する。</div>
            </div>

            <div class="collection">
                <h3>Vue compile</h3>
                <div class="memo">コンパイルして画面へレンダリングするまでを行ってくれているみたい？<br>他の表示が上書きされてしまうので今は非表示<br>後で調べてみて可能ならサンプルの1つとして表示する。</div>
            </div>

            <div class="collection">
                <h3>Vue version</h3>
                <div>{{ version }}</div>
            </div>
        </div>
        <script>

        // Component1
        Vue.component('my-component1',{ template: '<strong>Hello!!</strong>' });
        
        // Component2
        var MyComponent2 = Vue.extend({ template: '<strong>Hello!!</strong>' });
        Vue.component('my-component2', MyComponent2);

        // Directive
        Vue.directive('myfont', {
            inserted: function(el){
                el.style.fontSize = '48pt'
            }
        });

        // Fillter
        Vue.filter('toupper', function(value) {
            return value.toUpperCase();
        });

        // myPulgin
        // Vue.use(MyPlugin);

        // mixin
        Vue.mixin({
            created: function() {
                console.log(this);
            }
        });

        // compile
        var res = Vue.compile('<div>{{ message2 }}</div>');

        var app = new Vue({
            el: '#app',
            data: {
                message1: 'Hello!!',
                message2: 'Hello!!',
                colors: {black:'#000000', white:'#FFFFFF'},
                version: Vue.version,
            },
            // render: res.render,
            // staticRenderFns: res.staticRenderFns,
            methods: {
                addColor: function() {
                    Vue.set(this.colors, 'blue', '#0000FF');
                },
                deleteColor: function() {
                    Vue.delete(this.colors, 'blue');
                }
            }
        })

        // nextTick
        console.log('nextTick before: ' + app.message1);
        app.message1 = 'Bye!';
        Vue.nextTick(function() {
            console.log('nextTick after: ' + app.message1);
        })

        </script>
    </body>
</html>