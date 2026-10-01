[index.html.html](https://github.com/user-attachments/files/32902642/index.html.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Environment Vocabulary Quiz (A2)</title>
<link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{--bg:#E9F3EF;--card:#FFFFFF;--ink:#12303A;--muted:#4F6A72;--line:#BFD6CE;--accent:#176B87;--accent-ink:#FFFFFF;--ok:#1E7A4C;--okbg:#DDF3E6;--bad:#B3402A;--badbg:#FBE4DE;
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0F1F24;--card:#172C33;--ink:#E6F2EF;--muted:#9DB7B5;--line:#2C4650;--accent:#5FB6D1;--accent-ink:#0F1F24;--ok:#6FD39B;--okbg:#17382A;--bad:#F09A86;--badbg:#3D211B}}
:root[data-theme="dark"]{--bg:#0F1F24;--card:#172C33;--ink:#E6F2EF;--muted:#9DB7B5;--line:#2C4650;--accent:#5FB6D1;--accent-ink:#0F1F24;--ok:#6FD39B;--okbg:#17382A;--bad:#F09A86;--badbg:#3D211B}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*,*::before,*::after{box-sizing:inherit}
body{margin:0;background:var(--bg);color:var(--ink);font-family:"Atkinson Hyperlegible",system-ui,-apple-system,"Segoe UI",Arial,sans-serif;font-size:1.05rem;line-height:1.5}
[hidden]{display:none!important}
main{max-width:640px;margin:0 auto;padding:28px 18px 56px}
h1{font-size:1.9rem;line-height:1.15;margin:0 0 4px;letter-spacing:-.01em}
.sub{margin:0 0 22px;color:var(--muted)}
.meter{height:8px;background:var(--line);border-radius:99px;overflow:hidden}
#bar{height:100%;width:0;background:var(--accent);transition:width .3s}
#count{margin:8px 0 18px;color:var(--muted);font-size:.95rem}
.card{background:var(--card);border:1px solid var(--line);border-radius:16px;padding:22px 20px}
#prompt{font-size:1.45rem;font-weight:700;line-height:1.3;margin:0 0 18px}
#opts{display:grid;gap:10px}
.opt,.btn{font:inherit;cursor:pointer;border-radius:12px;text-align:left}
.opt{width:100%;padding:14px 16px;border:2px solid var(--line);background:var(--card);color:var(--ink);font-size:1.1rem;transition:border-color .15s,background .15s}
.opt:hover:not(:disabled){border-color:var(--accent)}
.opt:disabled{cursor:default;opacity:.65}
.opt.ok{opacity:1;border-color:var(--ok);background:var(--okbg);font-weight:700}
.opt.bad{opacity:1;border-color:var(--bad);background:var(--badbg);font-weight:700}
#fb{margin-top:16px;padding:14px 16px;border-radius:12px;background:var(--bg);border-left:5px solid var(--accent)}
#fb strong{display:block}
.btn{margin-top:16px;padding:13px 22px;border:0;background:var(--accent);color:var(--accent-ink);font-weight:700;font-size:1.05rem;text-align:center}
.btn:hover{filter:brightness(1.08)}
:focus-visible{outline:3px solid var(--accent);outline-offset:3px}
#score{font-size:3.2rem;font-weight:700;margin:0;line-height:1}
#msg{margin:10px 0 0}
@media (prefers-reduced-motion:reduce){*{transition:none!important}}
</style>
</head>
<body>
<main>
  <h1>Environment words</h1>
  <p class="sub">A2 vocabulary quiz, 10 questions. Choose the best answer.</p>

  <section id="quiz">
    <div class="meter" aria-hidden="true"><div id="bar"></div></div>
    <p id="count"></p>
    <div class="card">
      <p id="prompt"></p>
      <div id="opts"></div>
      <div id="fb" aria-live="polite" hidden></div>
      <button id="next" class="btn" hidden></button>
    </div>
  </section>

  <section id="result" class="card" hidden>
    <p id="score"></p>
    <p id="msg"></p>
    <button id="again" class="btn">Try again</button>
  </section>
</main>
<script>
var Q=[
["The Earth is getting hotter every year. This problem is called ...",["global warming","recycling","reusing","bicycle path"],0,"Global warming means the temperature of the Earth is slowly going up."],
["Carbon dioxide (CO\u2082) is a ... gas. It makes the Earth warmer.",["renewable","greenhouse","electric","recycled"],1,"Greenhouse gases, like CO\u2082, keep heat in the air around the Earth."],
["The greenhouse effect keeps the Earth ...",["cold","dark","warm","empty"],2,"The greenhouse effect traps heat from the sun. Too much of it causes global warming."],
["We put old bottles and paper in special bins so they can become new things. This is ...",["recycling","pollution","global warming","a carbon footprint"],0,"Recycling means making new things from old materials."],
["Solar power and wind power are examples of ...",["greenhouse gases","fossil fuels","renewable energy","waste"],2,"Renewable energy comes from sources that never finish, like the sun and the wind."],
["The amount of CO\u2082 that a person or a company produces is their ...",["bicycle path","carbon footprint","recycling bin","energy bill"],1,"Your carbon footprint is the CO\u2082 you produce when you travel, eat, and use energy."],
["Buying fewer things and using less water and electricity is called ...",["reusing","recycling","reducing consumption","polluting"],2,"Reducing consumption means using less. It is the best way to help the planet."],
["I don't throw away my glass jars. I use them again to keep food. I am ...",["reusing","wasting","burning","producing"],0,"Reusing means using something again, without changing it."],
["Cyclists can ride safely on special roads called ...",["highways","parking lots","bicycle paths","railways"],2,"Bicycle paths (or bike lanes) are roads only for bikes. They help people leave their cars at home."],
["Which of these is better for the environment than a petrol car?",["A big truck","A plane","An electric bike","A motorbike"],2,"Electric bikes and electric cars don't produce exhaust gases, so they pollute less than petrol vehicles."]
];
var i=0,score=0;
function $(s){return document.querySelector(s)}
function show(){
  var q=Q[i];
  $('#count').textContent='Question '+(i+1)+' of '+Q.length;
  $('#bar').style.width=(i/Q.length*100)+'%';
  $('#prompt').textContent=q[0];
  var o=$('#opts');o.innerHTML='';
  q[1].forEach(function(t,k){
    var b=document.createElement('button');
    b.className='opt';b.textContent=t;
    b.onclick=function(){pick(k)};
    o.appendChild(b);
  });
  $('#fb').hidden=true;$('#next').hidden=true;
}
function pick(k){
  var q=Q[i],right=k===q[2];
  document.querySelectorAll('.opt').forEach(function(b,j){
    b.disabled=true;
    if(j===q[2]){b.classList.add('ok');b.textContent='\u2713 '+q[1][j]}
    else if(j===k){b.classList.add('bad');b.textContent='\u2717 '+q[1][j]}
  });
  if(right)score++;
  var fb=$('#fb');
  fb.innerHTML='<strong>'+(right?'Correct!':'Not quite.')+'</strong>';
  fb.appendChild(document.createTextNode(q[3]));
  fb.hidden=false;
  var n=$('#next');
  n.textContent=i===Q.length-1?'See my score':'Next question';
  n.hidden=false;n.focus();
}
$('#next').onclick=function(){
  i++;
  if(i<Q.length){show()}else{
    $('#quiz').hidden=true;$('#result').hidden=false;
    $('#score').textContent=score+' / '+Q.length;
    $('#msg').textContent=score>=9?'Excellent! You know these words very well.':score>=6?'Good work! Practise the words you missed.':'Keep going! Read the explanations and try again.';
    $('#again').focus();
  }
};
$('#again').onclick=function(){
  i=0;score=0;$('#result').hidden=true;$('#quiz').hidden=false;show();
};
show();
</script>
</body>
</html>
