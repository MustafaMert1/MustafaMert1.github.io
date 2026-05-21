<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Furkan Öztaş Kuyumculuk - Canlı Fiyatlar</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Montserrat:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --text-main: #212529;
            --text-muted: #6c757d;
            --gold-primary: #c5a059;
            --gold-light: #f3eedf;
            --border-color: #e9ecef;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            width: 100%;
            background: var(--card-bg);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            padding: 30px;
            box-sizing: border-box;
            border-top: 5px solid var(--gold-primary);
        }

        /* Header Tasarımı */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid var(--gold-light);
            padding-bottom: 20px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo-area {
            text-align: center;
        }

        .logo-text {
            font-family: 'Playfair Display', serif;
            font-size: 28px;
            font-weight: 700;
            color: var(--gold-primary);
            letter-spacing: 1px;
            margin: 0;
        }

        .contact-info {
            font-size: 14px;
            font-weight: 600;
            text-align: right;
            color: var(--text-muted);
        }

        .contact-info span {
            display: block;
            color: var(--text-main);
        }

        .payment-banner {
            text-align: center;
            background-color: var(--gold-light);
            color: #8c6b32;
            padding: 15px;
            border-radius: 8px;
            font-weight: 600;
            margin-bottom: 30px;
            font-size: 15px;
        }

        .payment-banner strong {
            color: #d32f2f;
        }

        /* Tablo Tasarımı */
        .tables-wrapper {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--card-bg);
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
        }

        th {
            background-color: var(--gold-primary);
            color: white;
            font-weight: 600;
            padding: 15px 10px;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        td {
            padding: 15px 10px;
            text-align: center;
            border-bottom: 1px solid var(--border-color);
            font-size: 22px;
            font-weight: 700;
        }

        td:first-child {
            font-size: 14px;
            font-weight: 600;
            text-align: left;
            color: var(--text-muted);
        }

        tr:last-child td {
            border-bottom: none;
        }

        tr:hover {
            background-color: #fafafa;
        }

        /* Liste fiyatı üzerini çizme */
        .strike {
            text-decoration: line-through;
            color: #999;
            font-size: 18px;
            font-weight: 500;
        }

        /* Alt Bilgi */
        footer {
            margin-top: 30px;
            text-align: center;
            font-size: 14px;
            color: var(--text-muted);
            font-weight: 500;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
        }

        .timestamp {
            font-weight: 700;
            color: var(--gold-primary);
        }

        /* Mobil Uyumluluk */
        @media (max-width: 900px) {
            .tables-wrapper {
                grid-template-columns: 1fr;
            }
            header {
                flex-direction: column;
                text-align: center;
            }
            .contact-info {
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <div class="logo-area">
                <h1 class="logo-text">FURKAN ÖZTAŞ</h1>
                <span style="letter-spacing: 3px; font-size: 12px; color: var(--text-muted);">KUYUMCULUK</span>
            </div>
            
            <div class="contact-info">
                <span>📞 0332 351 51 11</span>
                <span>📱 0538 651 57 31</span>
            </div>
        </header>

        <div class="payment-banner">
            Kredi kartı ve mail Order ile <strong>tek çekim veya 3 taksit</strong> ödeme kolaylığı hizmetinizde
        </div>

        <div class="tables-wrapper">
            <table id="table-left">
                <thead>
                    <tr>
                        <th>Ürün</th>
                        <th>Alış Fiyatı</th>
                        <th>Liste Fiyatı</th>
                        <th>İndirimli</th>
                    </tr>
                </thead>
                <tbody id="tbody-left">
                    <tr><td colspan="4" style="font-size:14px;">Yükleniyor...</td></tr>
                </tbody>
            </table>

            <table id="table-right">
                <thead>
                    <tr>
                        <th>Ürün</th>
                        <th>Alış Fiyatı</th>
                        <th>Liste Fiyatı</th>
                        <th>İndirimli</th>
                    </tr>
                </thead>
                <tbody id="tbody-right">
                    <tr><td colspan="4" style="font-size:14px;">Yükleniyor...</td></tr>
                </tbody>
            </table>
        </div>

        <footer>
            Sistemimiz 1 dakika gecikmeli çalışmaktadır.<br>
            Son Güncelleme: <span id="last-update" class="timestamp">--:--</span>
        </footer>
    </div>

    <script>
        // Google Sheets ID ve GID
        const SHEET_ID = '12PVBJ0OrpewrVomn_x5NLHE7jAHgmZnbZkcORgrZYm4';
        const GID = '1292736467';
        
        // Bu URL, e-tabloyu CSV formatında çeker (Web'de Yayınla adımı zorunludur)
        const CSV_URL = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/export?format=csv&gid=${GID}`;

        // Zamanı güncelleme fonksiyonu
        function updateTime() {
            const now = new Date();
            const timeString = now.toLocaleDateString('tr-TR') + ' ' + now.toLocaleTimeString('tr-TR', { hour: '2-digit', minute: '2-digit' });
            document.getElementById('last-update').innerText = timeString;
        }

        // Veriyi çekip ekrana basma
        async function fetchGoldPrices() {
            try {
                const response = await fetch(CSV_URL);
                if (!response.ok) throw new Error("Veri çekilemedi. Tablonun 'Webde Yayınla' ayarını kontrol edin.");
                
                const csvText = await response.text();
                parseAndRenderCSV(csvText);
                updateTime();

            } catch (error) {
                console.error("Hata:", error);
                document.getElementById('tbody-left').innerHTML = '<tr><td colspan="4" style="color:red; font-size:14px;">Veri çekme hatası! Lütfen Google Sheets ayarlarını kontrol edin.</td></tr>';
                document.getElementById('tbody-right').innerHTML = '';
            }
        }

        function parseAndRenderCSV(csvData) {
            // Basit CSV Parser
            const rows = csvData.split('\n').map(row => row.split(',').map(cell => cell.replace(/"/g, '').trim()));
            
            let htmlLeft = '';
            let htmlRight = '';

            // Görseldeki tabloya göre satır indeksleri (Excel'in yapısına göre bu indeksleri ayarlaman gerekebilir)
            // Varsayım: Sol tablo ilk 7 satır, Sağ tablo sonraki 7 satır veya yan yana kolonlar.
            // Google Sheets tablonuz görseldeki gibi tasarlanmışsa, verileri manuel çekmek gerekebilir.
            
            // DEMO VERİ DOLDURMA (Görselinizdeki yapıya uygun statik şablon oluşturucu)
            // Eğer Google Sheets verileriniz görseldeki gibi sağ/sol hücrelere dağılmışsa 
            // array indekslerini [row][col] şeklinde belirtebilirsiniz. 
            // Aşağıdaki yapı örnek olarak görseldeki verilerle doldurulmuştur. Gerçek veriyi 'rows' değişkeninden alabilirsiniz.

            // Sol Tablo Statik Örnek:
            const leftData = [
                { name: "24 AYAR GRAM<br><small>(50-100)</small>", buy: rows[2]?.[1] || "6583", list: rows[2]?.[2] || "7050", discount: rows[2]?.[3] || "6662" },
                { name: "24 AYAR GRAM<br><small>(5-10-20)</small>", buy: rows[3]?.[1] || "6596", list: rows[3]?.[2] || "7060", discount: rows[3]?.[3] || "6672" },
                { name: "24 AYAR GRAM<br><small>(1 GRAMLIK)</small>", buy: rows[4]?.[1] || "6603", list: rows[4]?.[2] || "7074", discount: rows[4]?.[3] || "6686" },
                { name: "22 AYAR BİLEZİK", buy: rows[5]?.[1] || "6016", list: rows[5]?.[2] || "7112", discount: rows[5]?.[3] || "6259" },
                { name: "18 AYAR ÜRÜNLER", buy: rows[6]?.[1] || "4749", list: rows[6]?.[2] || "0", discount: rows[6]?.[3] || "0" },
                { name: "14 AYAR ÜRÜNLER", buy: rows[7]?.[1] || "3760", list: rows[7]?.[2] || "6162", discount: rows[7]?.[3] || "5238" },
                { name: "8 AYAR ÜRÜNLER", buy: rows[8]?.[1] || "1979", list: rows[8]?.[2] || "4199", discount: rows[8]?.[3] || "3570" },
            ];

            const rightData = [
                { name: "ÇEYREK", buy: rows[2]?.[6] || "10620", list: rows[2]?.[7] || "11579", discount: rows[2]?.[8] || "10943" },
                { name: "YARIM", buy: rows[3]?.[6] || "21240", list: rows[3]?.[7] || "23088", discount: rows[3]?.[8] || "21818" },
                { name: "TAM", buy: rows[4]?.[6] || "42349", list: rows[4]?.[7] || "45894", discount: rows[4]?.[8] || "43370" },
                { name: "GREMSE", buy: rows[5]?.[6] || "106202", list: rows[5]?.[7] || "114735", discount: rows[5]?.[8] || "108425" },
                { name: "ATA LİRA", buy: rows[6]?.[6] || "43734", list: rows[6]?.[7] || "47235", discount: rows[6]?.[8] || "44638" },
                { name: "GÜMÜŞ", buy: rows[7]?.[6] || "106", list: rows[7]?.[7] || "126", discount: rows[7]?.[8] || "120" },
                { name: "ONS ALTIN", buy: rows[8]?.[6] || "4532", list: rows[8]?.[7] || "-", discount: rows[8]?.[8] || "4532" },
            ];

            // Tabloyu Oluştur (Liste fiyatında 0 olanları veya #DIV/0! olanları temizleme mantığı ile)
            leftData.forEach(item => {
                let listPrice = (item.list === "0" || item.list === "" || item.list === "#DIV/0!") ? "-" : `<span class="strike">${item.list}</span>`;
                let discPrice = (item.discount === "0") ? "-" : item.discount;
                htmlLeft += `<tr><td>${item.name}</td><td>${item.buy}</td><td>${listPrice}</td><td>${discPrice}</td></tr>`;
            });

            rightData.forEach(item => {
                let listPrice = (item.list === "0" || item.list === "" || item.list === "#DIV/0!") ? "-" : `<span class="strike">${item.list}</span>`;
                let discPrice = (item.discount === "0") ? "-" : item.discount;
                htmlRight += `<tr><td>${item.name}</td><td>${item.buy}</td><td>${listPrice}</td><td>${discPrice}</td></tr>`;
            });

            document.getElementById('tbody-left').innerHTML = htmlLeft;
            document.getElementById('tbody-right').innerHTML = htmlRight;
        }

        // Sayfa yüklendiğinde ve her 60 saniyede bir veriyi çek
        window.onload = () => {
            fetchGoldPrices();
            setInterval(fetchGoldPrices, 60000); // 1 dakikada bir yeniler
        };
    </script>
</body>
</html>
