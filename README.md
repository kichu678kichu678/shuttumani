index. html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Where We Sat</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:"Georgia", serif;
}

body{
  min-height:100vh;
  background:linear-gradient(#f7efe5,#e6d3b1);
  display:flex;
  flex-direction:column;
  align-items:center;
  color:#4b3621;
}

/* HEADER */
header{
  padding:25px;
  font-size:2rem;
  letter-spacing:1px;
}

/* CLASSROOM */
.classroom{
  width:100%;
  max-width:900px;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:35px;
  padding-bottom:60px;
}

/* BENCH ROW */
.row{
  display:flex;
  gap:30px;
}

/* BENCH */
.bench{
  width:180px;
  height:90px;
  background:linear-gradient(#c89b6d,#8b5a2b);
  border-radius:12px;
  position:relative;
  box-shadow:0 10px 0 #5a3e2b;
  cursor:pointer;
  transition:all 0.3s ease;
}

.bench:hover{
  transform:translateY(-6px);
}

/* BENCH LEGS */
.bench::before,
.bench::after{
  content:"";
  position:absolute;
  bottom:-30px;
  width:22px;
  height:30px;
  background:#5a3e2b;
  border-radius:0 0 6px 6px;
}

.bench::before{ left:18px; }
.bench::after{ right:18px; }

/* BENCH GLOW (MAGIC MEMORY) */
.bench.active{
  box-shadow:0 0 25px rgba(255,200,150,0.8),
             0 10px 0 #5a3e2b;
}

/* STORY BOX */
.story{
  margin-top:40px;
  width:90%;
  max-width:700px;
  min-height:120px;
  background:rgba(255,255,255,0.6);
  border-radius:15px;
  padding:20px;
  font-size:1.1rem;
  line-height:1.6;
  text-align:center;
  box-shadow:0 8px 20px rgba(0,0,0,0.1);
  opacity:0;
  transform:translateY(20px);
  transition:all 0.4s ease;
}

.story.show{
  opacity:1;
  transform:translateY(0);
}

/* FOOTNOTE */
.footer{
  margin-top:20px;
  opacity:0.7;
  font-size:0.95rem;
}

/* MOBILE */
@media(max-width:600px){
  .bench{
    width:130px;
    height:70px;
  }
}
</style>
</head>

<body>

<header>
  🌸 The Classroom That Remembers 🌸
</header>

<section class="classroom">

  <div class="row">
    <div class="bench" data-story="That first bench… where silence felt louder than words."></div>
    <div class="bench" data-story="We sat here pretending to listen, but noticing only each other."></div>
  </div>

  <div class="row">
    <div class="bench" data-story="This bench knows about stolen glances and shy smiles."></div>
    <div class="bench" data-story="Someone carved initials here. The chalk erased them, but not the feeling."></div>
  </div>

  <div class="row">
    <div class="bench" data-story="Rain outside. Notes unfinished. Hearts loud."></div>
    <div class="bench" data-story="If benches could speak, this one would blush first."></div>
  </div>

  <div id="storyBox" class="story"></div>

  <div class="footer">
    Click a bench. Let it remember.
  </div>

</section>

<script>
const benches = document.querySelectorAll(".bench");
const storyBox = document.getElementById("storyBox");

benches.forEach(bench=>{
  bench.addEventListener("click",()=>{
    benches.forEach(b=>b.classList.remove("active"));
    bench.classList.add("active");

    const text = bench.getAttribute("data-story");
    storyBox.textContent = text;
    storyBox.classList.add("show");
  });
});
</script>

</body>
</html>
