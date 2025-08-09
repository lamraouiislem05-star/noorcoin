document.body.style.margin = "0";
document.body.style.fontFamily = "Arial, sans-serif";
document.body.style.backgroundColor = "#000";
document.body.style.color = "#FFD700";
document.body.style.textAlign = "center";
document.body.style.padding = "0";

// إنشاء الحاوية الرئيسية
let container = document.createElement("div");
container.style.maxWidth = "800px";
container.style.margin = "auto";
container.style.padding = "20px";

// الشعار
let logo = document.createElement("img");
logo.src = "logo.png"; // ضع رابط شعار العملة هنا
logo.style.width = "150px";
logo.style.marginTop = "20px";
container.appendChild(logo);

// العنوان
let title = document.createElement("h1");
title.innerText = "🚀 NoorCoin (NRC)";
title.style.color = "#FFD700";
container.appendChild(title);

// السعر
let priceDiv = document.createElement("div");
priceDiv.className = "price";
priceDiv.style.fontSize = "1.5rem";
priceDiv.innerText = "💰 السعر الآن: جاري التحميل...";
container.appendChild(priceDiv);

// زر الشراء
let buyBtn = document.createElement("a");
buyBtn.href = "https://jup.ag/tokens/GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump";
buyBtn.innerText = "💳 Buy Now";
buyBtn.style.display = "inline-block";
buyBtn.style.backgroundColor = "#FFD700";
buyBtn.style.color = "#000";
buyBtn.style.padding = "10px 20px";
buyBtn.style.margin = "20px";
buyBtn.style.textDecoration = "none";
buyBtn.style.borderRadius = "5px";
container.appendChild(buyBtn);

// رابط الجروب
let groupLink = document.createElement("a");
groupLink.href = "https://t.me/noorocoin";
groupLink.innerText = "📢 Join Telegram";
groupLink.style.display = "inline-block";
groupLink.style.backgroundColor = "#FFD700";
groupLink.style.color = "#000";
groupLink.style.padding = "10px 20px";
groupLink.style.margin = "20px";
groupLink.style.textDecoration = "none";
groupLink.style.borderRadius = "5px";
container.appendChild(groupLink);

// إضافة الحاوية للصفحة
document.body.appendChild(container);

// دالة تحديث السعر
async function updatePrice() {
    try {
        let res = await fetch("https://price.jup.ag/v4/price?ids=GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump");
        let data = await res.json();
        let price = data.data["GZJXJtctfsKJ3mk1jHQVTi5WzPupqtEYNHFmyV2Fpump"].price;
        priceDiv.innerText = `💰 السعر الآن: ${price.toFixed(4)}$`;
    } catch (e) {
        priceDiv.innerText = "⚠️ تعذر جلب السعر";
        console.error(e);
    }
}

// تحديث أولي + تحديث كل 30 ثانية
updatePrice();
setInterval(updatePrice, 30000);
