<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MrBerk Analiz Tablosu</title>
<style>
body {
    margin: 0;
    background: radial-gradient(circle, #020617, #000);
    color: white;
    font-family: Arial, sans-serif;
    text-align: center;
    padding: 20px;
}

h1 {
    color: gold;
    font-size: 36px;
    margin-bottom: 10px;
    text-shadow: 0 0 15px gold;
}

.subtitle {
    font-size: 18px;
    color: #22c55e;
    margin-bottom: 30px;
    text-shadow: 0 0 10px #22c55e;
}

.rulet-masa {
    display: grid;
    grid-template-columns: repeat(12, 50px);
    gap: 8px;
    justify-content: center;
    margin-bottom: 30px;
}

.rulet-num {
    width: 50px;
    height: 50px;
    line-height: 50px;
    border-radius: 6px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
    color: white;
    text-shadow: 0 0 5px black;
    border: 2px solid #22c55e;
}

.rulet-num:hover {
    transform: scale(1.2);
    box-shadow: 0 0 15px #22c55e;
}

.rulet-num.red { background: #b71c1c; }
.rulet-num.black { background: #212121; }
.rulet-num.green { background: #2e7d32; }

#sonuc {
    font-size: 28px;
    color: gold;
    margin-top: 20px;
    min-height: 50px;
    text-shadow: 0 0 15px gold;
}

.loading {
    color: #94a3b8;
    font-size: 20px;
}

/* Slot animasyonu */
.slot {
    display: inline-block;
    margin: 0 5px;
    padding: 10px 15px;
    background: #111;
    border: 2px solid #22c55e;
    border-radius: 6px;
    color: white;
    font-weight: bold;
    animation: spinAnim 0.5s ease-in-out;
}

@keyframes spinAnim {
    0% { transform: translateY(-30px); opacity: 0; }
    50% { transform: translateY(10px); opacity: 1; }
    100% { transform: translateY(0); opacity: 1; }
}
</style>
</head>
<body>

<h1>MrBerk Analiz Tablosu</h1>
<div class="subtitle">5’li KOMŞUDAN OYNAYIN</div>

<div class="rulet-masa" id="ruletMasa"></div>

<div id="sonuc"></div>

<script>
// Sayı eşleşmeleri
const sayiEslestirmeleri = {
0:[32,24],1:[32,1],2:[4,14],3:[32,24],4:[24,34],
5:[5,35],6:[36,28],7:[7,21],8:[8,28],9:[18,27],
10:[5,29],11:[12,13],12:[12,25],13:[13,14],14:[12,27],
15:[15,14],16:[25,14],17:[17,18],18:[9,27],19:[18,36],
20:[20,35],21:[21,5],22:[20,25],23:[32,33],24:[2,24],
25:[25,22],26:[6,16],27:[27,9],28:[8,9],29:[30,9],
30:[30,29],31:[13,26],32:[21,20],33:[31,13],34:[34,35],
35:[35,17],36:[34,33]
};

// Rulet renkleri (kırmızı/siyah/yeşil)
const redNumbers = [1,3,5,7,9,12,14,16,18,19,21,23,25,27,30,32,34,36];
const blackNumbers = [2,4,6,8,10,11,13,15,17,20,22,24,26,28,29,31,33,35];

const ruletMasaDiv = document.getElementById("ruletMasa");
for (let i=0;i<=36;i++){
    let btn = document.createElement("div");
    btn.classList.add("rulet-num");
    if(i===0) btn.classList.add("green");
    else if(redNumbers.includes(i)) btn.classList.add("red");
    else btn.classList.add("black");
    btn.innerText = i;
    btn.onclick = ()=>tahmin(i);
    ruletMasaDiv.appendChild(btn);
}

function tahmin(secim){
    const sonucDiv = document.getElementById("sonuc");
    sonucDiv.innerHTML="<span class='loading'>Analiz yapılıyor...</span>";
    
    setTimeout(()=>{
        const numbers = sayiEslestirmeleri[secim] || ["-"];
        // Slot animasyonu için her sayıyı span ile göster
        sonucDiv.innerHTML = "";
        numbers.forEach(num=>{
            const span = document.createElement("span");
            span.classList.add("slot");
            span.innerText = num;
            sonucDiv.appendChild(span);
        });
    },1500);
}
</script>

</body>
</html>
