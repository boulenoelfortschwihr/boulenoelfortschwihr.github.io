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
    <img src="[model1.png](http://1.bp.blogspot.com/-DMBqlt1Mn-g/VIL_WFGreNI/AAAAAAADOF0/jrIx42p4hMI/s1600/clipart%2Bnavide%C3%B1os%2B(3)%2B(1).png)" class="model-thumb" onclick="selectModel(4)">
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
