<!DOCTYPE html>
<html>
<head>
<title>AI Partner Chat</title>
<style>
body { font-family: Arial, sans-serif; max-width: 500px; margin: auto; padding: 20px; }
#chat { border: 1px solid #ccc; height: 300px; overflow-y: auto; padding: 10px; margin-bottom: 10px; }
.user { color: blue; margin: 5px 0; }
.ai { color: green; margin: 5px 0; }
textarea { width: 100%; height: 50px; }
button { width: 100%; padding: 10px; }
</style>
</head>
<body>
<h2>AI Partner Chat</h2>
<div id="chat"></div>
<textarea id="msg" placeholder="Type your message..."></textarea><br>
<button onclick="sendMessage()">Send</button>

<script>
function addMessage(text, sender) {
  const div = document.createElement("div");
  div.className = sender;
  div.textContent = text;
  document.getElementById("chat").appendChild(div);
  document.getElementById("chat").scrollTop = document.getElementById("chat").scrollHeight;
}

// Temporary: just echo user input until Zapier is connected
function sendMessage() {
  const msg = document.getElementById("msg").value;
  if(!msg) return;
  addMessage(msg, "user");
  addMessage("AI will reply here after Zapier processes.", "ai");
  document.getElementById("msg").value = "";
}
</script>
</body>
</html>
