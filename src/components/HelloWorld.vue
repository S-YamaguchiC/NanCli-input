<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <form id="n_form" action="CGIのパス" method="post">
            <p>選択肢 → [
                <input type="radio" name="b1" value="A" @click="addData" required>A
                <input type="radio" name="b1" value="B" @click="addData" required>B
                <input type="radio" name="b1" value="C" @click="addData" required>C
                <input type="radio" name="b1" value="D" @click="addData" required>D
                ]
            </p>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        },

        // つかう関数
        methods: {

            // ボタンが押されたときの処理
            addData: function () {
                alert(document.getElementById("n_form").b1.value)
                // cgiに値の送信

            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        display: inline-block;
        margin: 0 10px;
    }
    a {
        color: #42b983;
    }
</style>
