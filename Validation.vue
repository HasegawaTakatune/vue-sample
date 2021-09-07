<!DOCTYPE html>
<html lang="ja">
    <head>
        <meta charset="UTF-8">
        <title>Hello world</title>
        <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    </head>
    <body>

    <div id="app-2">
        <div>テスト</div>
        <input type="text" v-model="message">
        <div class="error" v-if="error.require">必須項目です。</div>
        <div class="error" v-if="error.tooLong">長すぎます。</div>
    </div>
    <script>
    var app2 = new Vue({
        el: '#app-2',
        watch:{
            message: function(newVal, oldVal){
                this.error.require = (newVal.length < 1) ? true : false;
                this.error.tooLong = (newVal.length > 5) ? true : false;
            }
        },
        data: {
            message: 'Hello',
            error: {
                require: false,
                tooLong: false,
            }
        }
    })
    </script>
    <style>
    #app-2 .error{
        color:red;
    }
    </style>
    </body>
</html>