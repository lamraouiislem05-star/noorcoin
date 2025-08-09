<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>$NRC Coin</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #000;
        color: white;
        text-align: center;
    }
    header {
        padding: 30px;
        animation: fadeIn 1.5s ease-in-out;
    }
    header img {
        max-width: 200px;
        animation: pulse 2s infinite;
    }
    h1 {
        font-size: 2.5em;
        color: gold;
    }
    p {
        font-size: 1.2em;
        max-width: 600px;
        margin: auto;
    }
    .price {
        font-size: 2em;
        color: gold;
        margin: 20px 0;
        animation: fadeInUp 1s ease-in-out;
    }
    a.button {
        display: inline-block;
        background: gold;
        color: black;
        padding: 15px 25px;
        margin: 10px;
        border-radius: 8px;
        text-decoration: none;
        font-weight: bold;
        transition: 0.3s;
    }
    a.button:hover {
        background: #ffcc00;
        transform: scale(1.05);
    }
    section {
        padding: 20px;
    }
    footer {
        background: #111;
        color: #aaa;
        padding: 15px;
        font-size: 0.9em;
        margin-top: 30px;
    }
    @keyframes pulse {
        0%, 100% { transform: scale(1); }
        50% { transform: scale(1.05); }
    }
    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }
    @keyframes fadeInUp {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }
</style>
</head>
<body>

<header>
    <img src="logo.png" alt="$NRC Logo">
    <h1>🚀 $NRC Coin</h1>
    <p>عملة نادرة، مجتمع صغير لكن طموحنا كبير 🌍</p>
</header>

<section>
    <div class="price">💰 السعر الآن: ...</div>
    <a href="https://jup.ag/tokens/GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump" class="button">🚀 Buy Now</a>
    <a href="https://t.me/noorocoin" class="button">📢 Join Telegram</a>
</section>

<section>
    <h2 style="color:gold;">🎁 Airdrop Offer</h2>
    <p>أول 20 شخص يعمل Retweet و ينضم للجروب يحصل على Airdrop مجاني!</p>
</section>

<footer>
    &copy; 2025 NRC Coin. All Rights Reserved.
</footer>

<script>
async function updatePrice() {
    try {
        let res = await fetch("https://price.jup.ag/v4/price?ids=GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump");
        let data = await res.json();
        let price = data.data["GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump"].price;
        document.querySelector(".price").innerHTML = `💰 السعر الآن: ${price.toFixed(4)}$`;
    } catch (e) {
        console.error("خطأ في جلب السعر", e);
    }
}
updatePrice();
setInterval(updatePrice, 30000);
</script>

</body>
</html>
