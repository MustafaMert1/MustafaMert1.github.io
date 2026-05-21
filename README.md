<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Benim Web Sitem</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #0f172a, #1e293b);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .kart {
            background: rgba(255,255,255,0.08);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 20px rgba(0,0,0,0.4);
            width: 350px;
        }

        h1 {
            margin-bottom: 10px;
        }

        p {
            color: #cbd5e1;
        }

        button {
            margin-top: 20px;
            padding: 12px 25px;
            border: none;
            border-radius: 10px;
            background: #3b82f6;
            color: white;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            background: #2563eb;
            transform: scale(1.05);
        }
    </style>
</head>

<body>

    <div class="kart">
        <h1>Merhaba Dünya 👋</h1>
        <p>Bu benim ilk modern HTML sayfam.</p>

        <button onclick="mesajGoster()">
            Tıkla
        </button>
    </div>

    <script>
        function mesajGoster() {
            alert("Butona tıkladın!");
        }
    </script>

</body>
</html>
