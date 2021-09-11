<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="./CSS/style.css">
        <title>Directive</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>
        <div id="app">
            <div class="collection">
                <h3>はじめに</h3>
                <span>ここの内容は<a href="https://www.tohoho-web.com/ex/vuejs.html">Vue.js入門 - とほほのＷＷＷ入門</a>に記述されているモノを写しているだけです。詳しく知りたければ自分で調べてね。<br>ここでは、初めに表示についてをいろいろ試しているよ。</span>
            </div>
            <div class="collection">
                <h3>Hello World!!</h3>
                {{ message1 }}
            </div>

            <div class="collection">
                <h3>Display1</h3>
                <h5>Normal</h5>
                <div>{{ message2 }}</div>
                <h5>v-text</h5>
                <div v-text="message2"></div>
                <h5>v-html</h5>
                <div v-html="message2"></div>
            </div>

            <div class="collection">
                <button onclick="location.reload()">再表示</button>
                <h3>Display2</h3>
                <h5>Normal</h5>
                <div>{{ message3 }}</div>
                <h5>v-cloak</h5>
                <div v-cloak>{{ message3 }}</div>
                <div class="memo">style.cssでv-cloakで表示準備が終わる（ロード終了）まで、非表示にしておく設定をしている。</div>
            </div>

            <div class="collection">
                <h3>Bind value</h3>
                <h5>v-model</h5>
                <input type="text" v-model="message4">
                <h5>display</h5>
                <div>{{ message4 }}</div>
                <h5>v-pre</h5>
                <div v-pre>{{ message4 }}</div>x
                <h5>v-once</h5>
                <div v-once>{{ message4 }}</div>
            </div>

            <div class="collection">
                <h3>Validation</h3>
                <input type="text" v-model="message5">
                <div class="error" v-if="error.require">必須項目です。</div>
                <div class="error" v-if="error.tooLong">文字が長すぎます。</div>
                <br>
                <div>入力した値</div>
                <div>{{ message5 }}</div>
            </div>

            <div class="collection">
                <h3>Check Box</h3>
                <input type="checkbox" @click="change" checked>
                <span v-show="showCheckMSG">Hello!!</span>
            </div>

            <div class="collection">
                <h3>Radio Button</h3>
                <div>
                    <input type="radio" name="showRadioTYP" onclick="app.showRadioTYP='A'" checked>A
                    <input type="radio" name="showRadioTYP" onclick="app.showRadioTYP='B'">B
                    <input type="radio" name="showRadioTYP" onclick="app.showRadioTYP='C'">C
                </div>
                <div>
                    <span v-if="showRadioTYP == 'A'">Good morning.</span>
                    <span v-else-if="showRadioTYP == 'B'">Hello!</span>
                    <span v-else="showRadioTYP == 'C'">Bye!</span>
                </div>
            </div>

            <div class="collection">
                <h3>Loop</h3>
                <ol>
                    <li v-for="color in colors">{{ color }}</li>
                </ol>
            </div>

            <div class="collection">
                <h3>Click Event</h3>
                <h5>Button</h5>
                <button v-on:click="hello">Hello</button>
                <br>
                <button @click="hello">Hello</button>
                <br>
                <h5>Input</h5>
                <input type="button" v-bind:value="label" @click="hello">
                <br>
                <input type="button" :value="label" @click="hello">
                <br>
                <input type="text" v-model="label">
            </div>

        </div>
        <script>
        var app = new Vue({
            el: '#app',
            watch: {
                message5: function(after, before){
                    this.error.require = (after.length < 1) ? true : false;
                    this.error.tooLong = (after.length > 14) ? true : false;
                }
            },
            data: {
                message1: 'Hello world!!',
                message2: '<br>Hello!!<br>',
                message3: 'Hello world!!',
                message4: 'Hello world!!',
                message5: 'Hello world!!',
                message6: 'Hello world!!',
                showCheckMSG: true,
                showRadioTYP: 'A',
                colors: ['Red', 'Green', 'Blue'],
                label: 'Hello!',
                error: {
                    require: false,
                    tooLong: false,
                }
            },
            methods: {
                change: function(event){
                    this.show = event.target.checked;
                },
                hello: function(){
                    alert('Hello!!');
                }
            }
        })
        </script>
    </body>
</html>