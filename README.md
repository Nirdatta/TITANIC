<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF‑8" />
  <meta name="viewport" content="width=device‑width, initial‑scale=1" />
  <title>IL TITANIC</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --navy: #344C65;
      --buff: #F1CF9F;
      --wood: #A67B5B;
      --text: #edf4f6;
      --glass-bg: rgba(255, 255, 255, 0.05);
      --blur: blur(20px);
    }
    *{box-sizing:border-box;margin:0;padding:0;}
    body{font-family:'Montserrat',sans-serif;background:var(--navy);color:var(--text);min-height:100vh;padding:40px 20px;display:flex;flex-direction:column;align-items:center;}
    h1{font-size:clamp(2.5rem,6vw,4rem);background:linear-gradient(90deg,var(--buff),var(--text));-webkit-background-clip:text;-webkit-text-fill-color:transparent;text-shadow:0 0 20px var(--buff);margin-bottom:10px;}
    p.subtitle{font-size:1.3rem;opacity:0.85;text-align:center;margin-bottom:30px;}
    .hero{width:100%;max-width:900px;border-radius:20px;overflow:hidden;box-shadow:0 0 40px rgba(0,0,0,0.4);margin-bottom:40px;}
    .hero img{width:100%;height:auto;display:block;opacity:0.95;transition:transform 1s ease;}
    .hero img:hover{transform:scale(1.03);}
    .search-box{max-width:600px;width:100%;backdrop-filter:var(--blur);background:var(--glass-bg);border-radius:20px;box-shadow:0 0 30px rgba(255,255,255,0.1);padding:20px;}
    input[type=text]{width:100%;padding:15px 20px;font-size:1.1rem;border-radius:15px;border:none;background:rgba(255,255,255,0.08);color:var(--text);backdrop-filter:var(--blur);outline:none;transition:box-shadow 0.3s;}
    input[type=text]:focus{box-shadow:0 0 25px rgba(241,207,159,0.6);}
    .results{margin-top:40px;width:100%;max-width:800px;}
    .section{display:none;background:var(--glass-bg);backdrop-filter:var(--blur);border-radius:20px;padding:20px;margin-bottom:20px;animation:fadeInUp 0.6s ease forwards;box-shadow:0 0 15px rgba(255,255,255,0.2);}
    .section h2{font-size:1.6rem;border-bottom:1px solid rgba(255,255,255,0.2);padding-bottom:8px;margin-bottom:10px;color:var(--buff);}
    .section p{font-size:1.05rem;line-height:1.6;opacity:0.9;}
    @keyframes fadeInUp{from{opacity:0;transform:translateY(20px);}to{opacity:1;transform:translateY(0);}}
    @media(max-width:600px){p.subtitle{font-size:1rem;} .section h2{font-size:1.4rem;} .section p{font-size:1rem;}}
  </style>
</head>
<body>

  <h1>IL TITANIC</h1>
  <p class="subtitle">Un sogno diventato realtà</p>

  <div class="hero">
    <img src="https://upload.wikimedia.org/wikipedia/commons/f/fd/RMS_Titanic_3.jpg" alt="Titanic storico" />
  </div>

  <div class="search-box">
    <input type="text" id="search" placeholder="Cerca: Chi siamo, Da dove, Come è stato fatto..." />
  </div>

  <div class="results">
    <div class="section" id="chi">
      <h2>Chi Siamo</h2>
      <p>Boris, 13 anni, mente e mani dietro questo sito: un giovane appassionato di storia, modellismo e sogni grandi come il Titanic.</p>
    </div>
    <div class="section" id="dove">
      <h2>Da Dove</h2>
      <p>Il progetto nasce a Carrè, tra colline e creatività, dove un’idea fatta di legno e passione prende vita.</p>
    </div>
    <div class="section" id="come">
      <h2>Come è stato fatto</h2>
      <p>Costruito in legno compensato con passione e cura da Boris, come un vero artigiano dell’anima.</p>
    </div>
  </div>

  <script>
    const searchInput=document.getElementById("search");
    const sections={chi:document.getElementById("chi"),dove:document.getElementById("dove"),come:document.getElementById("come")};
    const keywords={chi:["chi","chi siamo"],dove:["da dove","dove"],come:["come","realizzato","costruito","come è stato"]};
    function hideAll(){Object.values(sections).forEach(s=>s.style.display="none");}
    hideAll();
    searchInput.addEventListener("input",()=>{
      const v=searchInput.value.toLowerCase();
      hideAll();
      for(let k in keywords){
        if(keywords[k].some(w=>v.includes(w))) sections[k].style.display="block";
      }
    });
  </script>

</body>
</html>
