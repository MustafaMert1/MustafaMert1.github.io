<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="refresh" content="60">
    <title>Canlı Altın Fiyatları</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

<?php

$json = file_get_contents(
    "https://docs.google.com/spreadsheets/d/12PVBJ0OrpewrVomn_x5NLHE7jAHgmZnbZkcORgrZYm4/gviz/tq?tqx=out:json"
);

$json = substr($json, 47, -2);

$data = json_decode($json, true);

?>

<div class="header">
    <div>
        <h1>FURKAN ÖZTAŞ KUYUMCULUK</h1>
        <p>Canlı Fiyat Ekranı</p>
    </div>

    <div class="time">
        <?= date("d.m.Y H:i") ?>
    </div>
</div>

<table>

    <tr>
        <th>ÜRÜN</th>
        <th>ALIŞ</th>
        <th>SATIŞ</th>
        <th>İNDİRİMLİ</th>
    </tr>

    <tr>
        <td>24 AYAR GRAM</td>
        <td>6571</td>
        <td>7031</td>
        <td>6643</td>
    </tr>

    <tr>
        <td>22 AYAR BİLEZİK</td>
        <td>6004</td>
        <td>7091</td>
        <td>6241</td>
    </tr>

    <tr>
        <td>ÇEYREK</td>
        <td>10600</td>
        <td>11546</td>
        <td>10911</td>
    </tr>

    <tr>
        <td>YARIM</td>
        <td>21200</td>
        <td>23022</td>
        <td>21756</td>
    </tr>

    <tr>
        <td>TAM</td>
        <td>42268</td>
        <td>45763</td>
        <td>43246</td>
    </tr>

</table>

<div class="footer">
    Sistemimiz 1 dakika gecikmeli çalışmaktadır
</div>

</body>
</html>
