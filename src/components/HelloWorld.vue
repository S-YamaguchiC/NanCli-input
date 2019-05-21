<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <form id="n_form">
            <p>選択肢 → [
                <input type="radio" name="b1" value="1" @click="addData" required>1
                <input type="radio" name="b1" value="2" @click="addData" required>2
                <input type="radio" name="b1" value="3" @click="addData" required>3
                <input type="radio" name="b1" value="4" @click="addData" required>4
                ]
            </p>
        </form>
        <p v-text="textData">あいうえい</p>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {

        name: 'HelloWorld',
        props: {
            msg: String
        },

        data() {
            return {
                textData: null
            }
        },

        // つかう関数
        methods: {
            // ボタンが押されたときの処理
            addData: function () {
                // alert(document.getElementById("n_form").b1.value)
                var num = document.getElementById("n_form").b1.value

                axios.post("ここにバックエンドのリンク")
                    .then(send => {
                        this.textData = send.data.text + "で送信した"
                    },)
                    // .catch(err => {
                    //     this.textData = err.toString()
                    // })
                    .finally(this.textData = "そうしんなう")
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
