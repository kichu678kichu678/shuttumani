index.html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Test</title>
<style>
body{margin:0;background:black;color:white;height:100vh}
#lock{
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  height:100vh;
}
input{padding:10px;font-size:18px}
button{padding:10px;margin-top:10px}
</style>
</head>
<body>

<div id="lock">
  <h2>LOCK SCREEN</h2>
  <input id="p" placeholder="Enter password">
  <button onclick="go()">Unlock</button>
</div>

<script>
function go(){
  if(document.getElementById("p").value==="01032025"){
    alert("Unlocked");
  }
}
</script>

</body>
</html>
