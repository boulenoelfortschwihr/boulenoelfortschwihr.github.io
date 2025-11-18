<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Prévisualisation Boules de Noël</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #f6f6f6;
        padding: 20px;
        text-align: center;
    }
    h1 { color: #c40028; }
    #models { display: flex; flex-wrap: wrap; justify-content: center; margin-bottom: 20px; }
    .model-thumb {
        width: 120px;
        margin: 10px;
        cursor: pointer;
        border: 2px solid transparent;
        border-radius: 10px;
        transition: 0.2s;
    }
    .model-thumb:hover { border-color: #c40028; }
    .selected { border-color: #c40028 !important; }
    canvas {
        margin-top: 20px;
        background: white;
        box-shadow: 0 0 10px #0002;
        border-radius: 10px;
    }
</style>
</head>
<body>

<h1>Prévisualisation des Boules de Noël</h1>

<h3>Choisis un modèle :</h3>
<div id="models">
    <img src="[model1.png](https://www.bing.com/images/search?view=detailV2&ccid=ZPhBozlZ&id=A8729BA30C77E75E10D16990ECD056F2AAE0E235&thid=OIP.ZPhBozlZZKjZfHI9uIPiHwHaD5&mediaurl=https%3a%2f%2fstoryauth.com%2fwp-content%2fuploads%2f2024%2f07%2fPoki-Games-1.webp&cdnurl=https%3a%2f%2fth.bing.com%2fth%2fid%2fR.64f841a3395964a8d97c723db883e21f%3frik%3dNeLgqvJW0OyQaQ%26pid%3dImgRaw%26r%3d0&exph=1080&expw=2048&q=poki&FORM=IRPRST&ck=044F3C88FF4C1D19794A64F500C4AF65&selectedIndex=1&itb=0&adlt=strict)" class="model-thumb" onclick="selectModel(1)">
    <img src="model2.png" class="model-thumb" onclick="selectModel(2)">
    <img src="model3.png" class="model-thumb" onclick="selectModel(3)">
    <img src="model4.png" class="model-thumb" onclick="selectModel(4)">
    <img src="model5.png" class="model-thumb" onclick="selectModel(5)">
    <img src="model6.png" class="model-thumb" onclick="selectModel(6)">
    <img src="model7.png" class="model-thumb" onclick="selectModel(7)">
    <img src="model8.png" class="model-thumb" onclick="selectModel(8)">
    <img src="model9.png" class="model-thumb" onclick="selectModel(9)">
</div>

<input id="nameInput" type="text" placeholder="Prénom à inscrire" oninput="updateCanvas()" style="padding:8px;font-size:18px; width:250px;">
<br>

<canvas id="preview" width="450" height="450"></canvas>

<br><br>
<button onclick="downloadPNG()" style="padding:10px 20px;font-size:18px;background:#c40028;color:white;border:none;border-radius:8px;cursor:pointer;">
    Télécharger l’aperçu
</button>

<script>
let currentModel = 1;
const canvas = document.getElementById("preview");
const ctx = canvas.getContext("2d");

function selectModel(n) {
    currentModel = n;

    // Sélection visuelle
    document.querySelectorAll('.model-thumb').forEach((el, i) => {
        el.classList.toggle("selected", i === n - 1);
    });

    // Désactiver le prénom pour le modèle 9
    document.getElementById("nameInput").disabled = (n === 9);

    updateCanvas();
}

function updateCanvas() {
    const img = new Image();
    img.src = "model" + currentModel + ".png";

    img.onload = () => {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.drawImage(img, 0, 0, canvas.width, canvas.height);

        if (currentModel !== 9) {
            ctx.font = "50px Arial";
            ctx.fillStyle = "black";
            ctx.textAlign = "center";
            ctx.fillText(
                document.getElementById("nameInput").value,
                canvas.width / 2,
                canvas.height * 0.82
            );
        }
    };
}

function downloadPNG() {
    const link = document.createElement('a');
    link.download = "boule_noel.png";
    link.href = canvas.toDataURL();
    link.click();
}

selectModel(1);
</script>

</body>
</html>
