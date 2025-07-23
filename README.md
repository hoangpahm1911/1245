<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Gmail コピー ツール</title>
  <style>
    body { font-family: sans-serif; background-color: #f7f7f7; padding: 30px; }
    h2 { color: #333; }
    input, button {
      font-size: 16px;
      padding: 10px;
      margin: 10px 0;
      width: 100%;
      max-width: 400px;
    }
    button { background-color: #4CAF50; color: white; border: none; cursor: pointer; }
    button:hover { background-color: #45a049; }
    .copied { color: green; margin-top: 10px; }
  </style>
</head>
<body>

  <h2>📋 Gmail コピー ツール</h2>

  <label for="gmail">メールアドレスを入力：</label><br>
  <input type="text" id="gmail" placeholder="例：abc@gmail.com"><br>
  <button onclick="copyGmail()">📋 コピー</button>
  <p class="copied" id="status"></p>

  <script>
    function copyGmail() {
      const gmail = document.getElementById("gmail").value.trim();
      if (!gmail) {
        alert("メールアドレスを入力してください。");
        return;
      }
      navigator.clipboard.writeText(gmail).then(() => {
        document.getElementById("status").innerText = "✅ コピーしました: " + gmail;
      });
    }
  </script>

</body>
</html>
