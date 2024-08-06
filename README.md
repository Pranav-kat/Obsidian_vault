# Obsidian_vault
My Personal notes vault integrated with Github

Automating the notes publishing from Obsidian Vault to my personal Github repo.

Initial Configuration:
- Install the Github Publisher plugin
- Add the github details like username, repository and personal access token
- Create the notes with key share = true in the frontmatter
- Open the command palette to upload the active file
- Voila!! Your notes have been pushed to your repo.

Pro Tip: Refer the notes on Obsidian for better UI experience

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Joke App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Joke App</h1>
        <button id="new-joke-btn">Get a New Joke</button>
        <div id="joke-container">
            <p id="joke"></p>
        </div>
    </div>
    <script src="scripts.js"></script>
</body>
</html>

---

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 300px;
}

h1 {
    margin-bottom: 20px;
}

button {
    padding: 10px 20px;
    margin-bottom: 20px;
    cursor: pointer;
}

#joke-container {
    border-top: 1px solid #ddd;
    padding-top: 20px;
}

#joke {
    font-size: 18px;
}

---

document.getElementById('new-joke-btn').addEventListener('click', fetchJoke);

async function fetchJoke() {
    try {
        const response = await fetch('https://v2.jokeapi.dev/joke/Any');
        const data = await response.json();

        let jokeText = '';
        if (data.type === 'single') {
            jokeText = data.joke;
        } else {
            jokeText = `${data.setup} - ${data.delivery}`;
        }

        document.getElementById('joke').innerText = jokeText;
    } catch (error) {
        console.error('Error fetching the joke:', error);
        document.getElementById('joke').innerText = 'Failed to fetch a joke.';
    }
}

// Fetch a joke on initial load
fetchJoke();

----
const response = await fetch('https://v2.jokeapi.dev/joke/Programming');
