# Nanchatte-Clicker-input

## 説明しよう！
NanCli-outputとは、[これ](https://github.com/S-YamaguchiC/NanchatteClicker)の入力と出力を分けたうちの入力の部分である。以上  

## なんくり（入力）の処理の流れ
1. 起動します
2. 選択肢のボタンを押します
3. ``addData()``が呼ばれて、あるサーバー上のCGIに非同期通信で値を送信します
4. おわり