# 2fa-Code-Genrator
2FA Code Generator: A simple, privacy-focused website for generating Time-based One-Time Passwords (TOTP) directly in your browser.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2FA Code Generator</title>
    <style>
        /* Modern Mobile-Optimized CSS */
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background-color: #121212;
            color: #E0E0E0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        .container {
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        h1 {
            font-size: 1.5em;
            font-weight: 500;
            margin-bottom: 30px;
            letter-spacing: 1px;
        }

        .code-display {
            background-color: #1E1E1E;
            padding: 25px 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }

        #two-fa-code {
            font-family: 'Courier New', Courier, monospace;
            font-size: 3em;
            font-weight: bold;
            color: #4CAF50;
            letter-spacing: 5px;
            margin: 0;
        }

        .input-group {
            width: 100%;
            margin-bottom: 20px;
        }

        #secret-key {
            width: 100%;
            padding: 15px;
            border-radius: 8px;
            border: 1px solid #333;
            background-color: #242424;
            color: #E0E0E0;
            font-size: 1em;
            text-align: center;
            box-sizing: border-box;
        }

        #secret-key:focus {
            outline: none;
            border-color: #4CAF50;
        }

        .button-group {
            display: flex;
            gap: 10px;
            justify-content: center;
        }

        button {
            background-color: #4CAF50;
            color: #fff;
            padding: 15px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.3s ease;
            width: 100%;
        }

        button:hover {
            background-color: #5cb85c;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>2FA Authenticator</h1>
    <div class="code-display">
        <p id="two-fa-code">000 000</p>
    </div>
    <div class="input-group">
        <input type="text" id="secret-key" placeholder="Enter your secret key">
    </div>
    <div class="button-group">
        <button onclick="generateCode()">Generate Code</button>
        <button onclick="copyCode()">Copy</button>
    </div>
</div>

<script>
    /*
      Note: A functional 2FA generator requires a library to handle the TOTP algorithm (e.g., js-sha1, etc.).
      This is a placeholder for where the JavaScript logic would go.
    */
    function generateCode() {
        // This is where the JavaScript logic would live to:
        // 1. Get the secret key from the input.
        // 2. Use a TOTP library (e.g., js-totp) to generate the code based on the secret and current time.
        // 3. Update the #two-fa-code element with the new code.
        // 4. Implement a timer to update the code every 30 seconds.
        const secret = document.getElementById('secret-key').value;
        if (secret) {
            // Placeholder for actual logic
            document.getElementById('two-fa-code').innerText = '123 456'; 
        } else {
            document.getElementById('two-fa-code').innerText = 'No Key';
        }
    }

    function copyCode() {
        const code = document.getElementById('two-fa-code').innerText;
        if (code !== 'No Key' && code !== '000 000') {
            navigator.clipboard.writeText(code.replace(/\s/g, ''))
                .then(() => {
                    alert('Code copied!');
                })
                .catch(err => {
                    alert('Failed to copy code.');
                });
        }
    }
</script>

</body>
</html>
