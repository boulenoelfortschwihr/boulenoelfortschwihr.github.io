<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Boules de Noël – Collège Alice Mosnier</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
    body { margin: 0; font-family: Arial, sans-serif; background: #f7f9ff; overflow-x: hidden; }
    header { text-align: center; background: #b30000; color: white; padding: 40px 20px; }
    h1 { margin: 0; font-size: 2.3em; }
    .container { max-width: 1000px; margin: auto; padding: 30px; }
    .section { background: white; padding: 25px; border-radius: 15px; margin-bottom: 30px; box-shadow: 0 0 12px rgba(0,0,0,0.1); }
    .models { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px,1fr)); gap: 20px; }
    .models img { width: 100%; border-radius: 12px; box-shadow: 0 0 10px rgba(0,0,0,0.15); transition: transform .3s; }
    .models img:hover { transform: scale(1.08); }
    footer { background: #222; color: #eee; padding: 20px; text-align: center; font-size: .9em; }
    .snowflake { position: fixed; top: -10px; color: white; font-size: 1em; user-select: none; pointer-events: none; animation: fall linear infinite; }
    @keyframes fall { to { transform: translateY(110vh); } }
</style>
</head>

<body>

<script>
    function snow() {
        const chars = ["❅","❆","❄"];
        setInterval(() => {
            const el = document.createElement("div");
            el.className = "snowflake";
            el.textContent = chars[Math.floor(Math.random()*chars.length)];
            el.style.left = Math.random()*100 + "vw";
            el.style.fontSize = (Math.random()*10 + 10) + "px";
            el.style.animationDuration = (Math.random()*5 + 5) + "s";
            document.body.appendChild(el);
            setTimeout(() => el.remove(), 12000);
        }, 150);
    }
    snow();
</script>

<header>
    <h1>Boules de Noël personnalisées</h1>
    <p>Action réalisée par les élèves du Collège Alice Mosnier afin de soutenir le financement de l’échange scolaire avec l’Allemagne.</p>
</header>

<div class="container">

    <div class="section">
        En achetant une boule de Noël personnalisée, vous soutenez le projet d’échange culturel avec nos partenaires allemands. Les élèves proposent ces boules à leur entourage : famille, amis, voisins, collègues. Votre participation contribue directement à rendre ce voyage possible.
    </div>

    <div class="section">
        <h2>Modèles disponibles</h2>
        <div class="models">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule1.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule2.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule3.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule4.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule5.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule6.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule7.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule8.jpg">
            <img src="https://raw.githubusercontent.com/boulenoelfortschwihr/boulenoelfortschwihr.github.io/d0729f5cb5fea858026be9acd56e9868b93d77da/Boule9.jpg">
        </div>
    </div>

    <div class="section">
        <h2>Comment commander ?</h2>
        <ul>
            <li>Choisissez vos modèles.</li>
            <li>Pour les modèles personnalisables (1 à 8), indiquez le prénom souhaité.</li>
            <li>Remplissez le bon de commande papier.</li>
            <li>Un seul chèque par famille (ordre indiqué sur le flyer).</li>
            <li>Date limite : 25 novembre.</li>
            <li>Distribution prévue entre le 15 et le 19 décembre 2025.</li>
        </ul>
    </div>

    <div class="section" style="text-align:center;">
        Contact par SMS : <strong>06 95 75 19 75</strong> ou <strong>07 66 49 33 88</strong>
    </div>

</div>

<footer>
    Document réalisé par les élèves du Collège Alice Mosnier dans le cadre de l’échange scolaire au lac de Constance.
</footer>

</body>
</html>
