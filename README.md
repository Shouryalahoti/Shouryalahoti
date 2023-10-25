<!DOCTYPE html>
<html>
<head>
    <title>Letter Values</title>
</head>
<body>
    <h1>Letter Values</h1>
    <label for="inputWord">Enter a word:</label>
    <input type="text" id="inputWord">
    <button onclick="convertWord()">Convert</button>
    <p id="output"></p>

    <script>
        const letterValues = {
            'a': 0, 'b': 6, 'c': 9, 'd': 24, 'e': 50,
            'f': 90, 'h': 147, 'i': 221, 'j': 450, 'k': 605,
            'l': 792, 'm': 1014, 'n': 1274, 'o': 1575, 'p': 1920,
            'q': 2312, 'r': 2754, 's': 3249, 't': 3800, 'u': 4410,
            'v': 5782, 'w': 5819, 'x': 6624, 'y': 7500, 'z': 8450
        };

        function convertWord() {
            const inputWord = document.getElementById("inputWord").value.toLowerCase();
            let result = "";

            for (let i = 0; i < inputWord.length; i++) {
                const letter = inputWord[i];
                if (letterValues[letter] !== undefined) {
                    result += letterValues[letter] + "_";
                }
            }

            if (result.length > 0) {
                result = result.slice(0, -1); // Remove the trailing underscore
                document.getElementById("output").textContent = result;
            } else {
                document.getElementById("output").textContent = "Word not found or contains unsupported characters.";
            }
        }
    </script>
</body>
</html>
