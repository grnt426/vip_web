---
layout: default
title: VIP Invites
---

# Invites

<!-- Input section for new user and guild name -->
<div style="margin-bottom: 1em;">
  <label for="newUser">New User: </label>
  <input type="text" id="newUser" placeholder="Enter new user" oninput="updateMessage()" />
</div>

<div style="margin-bottom: 1em;">
  <label for="guildName">Guild Name: </label>
  <select id="guildName" onchange="updateMessage()">
    <option value="VIPower">VIPower</option>
    <option value="VIPain">VIPain</option>
    <option value="VIPerfect">VIPerfect</option>
    <option value="VIPheonix">VIPheonix</option>
    <option value="VIPrimal">VIPrimal</option>
  </select>
</div>

<!-- Display the updated welcome message -->
<p id="welcomeMessage">
  ┌(^∇')7 ★ Hey look everyone! ★ New friends! ★ Everyone please welcome NEW_USER to VIPower ★ ┌(^∇')/\<('-^)┐
</p>

<!-- Button to copy the welcome message -->
<button onclick="copyMessage()">Copy Message</button>

<script>
  function updateMessage() {
    // Get input values; if empty, use placeholders
    var newUser = document.getElementById("newUser").value || "NEW_USER";
    var guildName = document.getElementById("guildName").value || "GUILD_NAME";
    
    // Construct the message string
    var message = "┌(^∇')7 ★ Hey look everyone! ★ New friends! ★ Everyone please welcome " 
                  + newUser + " to " + guildName 
                  + " ★ ┌(^∇')/\\('-^)┐";
    
    // Update the text content of the paragraph
    document.getElementById("welcomeMessage").textContent = message;
  }
  
  function copyMessage() {
    // Retrieve the text from the welcome message
    var message = document.getElementById("welcomeMessage").textContent;
    
    // Use the Clipboard API to copy the text
    navigator.clipboard.writeText(message)
      .then(function() {
        alert("Message copied to clipboard!");
      })
      .catch(function(err) {
        alert("Error copying message: " + err);
      });
  }
</script>
