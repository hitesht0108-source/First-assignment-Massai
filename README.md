# Browser Games

Two responsive, dependency-free games built with HTML, CSS, and vanilla JavaScript. Open either HTML file directly in a browser; no installation or build step is required.

## Memory Game

Match pairs of cards and try to finish in as few moves as possible.

- Choose a 4x4 or 6x6 board
- Track moves, time, and star rating
- Save best scores in browser local storage
- Play with a mouse or keyboard

Open `memory-game.html` to play. Use Tab to focus a card, then press Enter or Space to flip it.

## Simon Says

Watch the sequence of colored pads and sounds, then repeat it. Each successful round adds another step.

- Four color pads with synthesized tones
- Use the mouse, touchscreen, or keys 1-4
- Toggle sound on or off
- Save your best level in browser local storage

Open `simon-says.html` to play, then select **Start game**.

## Run Locally

Both games work by opening their HTML files directly. To serve the project locally instead, run this command from the repository folder:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/memory-game.html` or `http://localhost:8000/simon-says.html`.

## Built With

- HTML5, CSS, and vanilla JavaScript
- Browser local storage for best scores
- No external libraries or dependencies