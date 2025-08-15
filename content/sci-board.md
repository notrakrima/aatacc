---
title: "Scientific Board Login"
---

<div id="password-gate" style="text-align: center; margin-top: 50px;">
  <h3>Scientific Board Access</h3>
  <p>Please enter the password to continue.</p>
  <form onsubmit="checkPassword(event)">
    <input type="password" id="password" placeholder="Password" required style="padding: 8px; font-size: 16px;">
    <br><br>
    <button type="submit" style="padding: 10px 20px; font-size: 16px;">Enter</button>
  </form>
  <p id="error-message" style="color: red; display: none; margin-top: 10px;">Incorrect password. Please try again.</p>
</div>

<script>
  function checkPassword(event) {
    event.preventDefault(); // Prevents the form from submitting the traditional way
    var password = document.getElementById('password').value;
    var errorMessage = document.getElementById('error-message');

    // The password is "isodesmic".
    // We check against a simple "hashed" version for minor obfuscation.
    // 'isodesmic' reversed is 'cimsedosi'
    if (password.split('').reverse().join('') === 'cimsedosi') {
      // Correct password, redirect to the secret page.
      window.location.href = '/internal/board-members/';
    } else {
      // Incorrect password, show error message.
      errorMessage.style.display = 'block';
    }
  }
</script>
