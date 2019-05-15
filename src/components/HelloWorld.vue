<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <form id="n_form">
            <p>選択肢 → [
                <input type="radio" name="b1" value="A" @click="addData" required>A
                <input type="radio" name="b1" value="B" @click="addData" required>B
                <input type="radio" name="b1" value="C" @click="addData" required>C
                <input type="radio" name="b1" value="D" @click="addData" required>D
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
                var unko = document.getElementById("n_form").b1.value

                // cgiに値の送信
                axios.get('CGIのパス'+ "?" + unko)
                    .then(loading => {
                        this.textData = loading.data.toString()
                    })
                    .catch(err => {
                        this.textData = '送信に失敗したで、ンフフｗ' + '\n : ' + err.toString()
                    });
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
