# Lantern Shadows 🕯️

A lantern keeps the night away. Spirits drift out of the dark toward the flame — make each one's hand shadow before it gets there.

**Play:** https://marie-6.github.io/fun-games/lantern-shadows/

## How to play
1. Click **Play with camera** and allow camera access.
2. A spirit appears in the dark: *"A RABBIT approaches."*
3. Make that hand gesture in front of the webcam and hold it for a moment. Its black shadow is cast on the wall and the spirit is banished.
4. Too slow and the flame flickers. Lose all three candles and the night wins.

Faster catches score more, and catches in a row build a combo (up to ×5). Spirits speed up as you go, and after the first 8 the hints disappear — you have to remember the gestures.

The top-right corner shows what the model is seeing right now (for example `seeing: Owl 72%`).

## Gestures
| Teachable Machine class | Spirit |
|---|---|
| Dog | 🐕 Hound |
| Bird | 🕊️ Dove |
| Owl | 🦉 Owl |
| Peace | 🐇 Rabbit |
| Fist | 🐌 Snail |
| Palm | 🦋 Butterfly |
| nothing | (no spirit — what the model sees while you wait) |

No camera? Use **Keyboard demo** and press keys 1–6 instead of gestures.

## How it works
The gestures are recognized by an image model trained in Google's [Teachable Machine](https://teachablemachine.withgoogle.com/), loaded with TensorFlow.js:
https://teachablemachine.withgoogle.com/models/5wNvyhI--/

To use your own model, train an Image Project, export it with **Upload (shareable link)**, and paste the link into the field on the start screen. Class names are matched to spirits by name (dog, bird, owl, peace, fist, palm); any other class shows a hand shadow labeled with its name. A class called `nothing` or `background` is ignored.

**Tips for training:** record every class in the room and light you'll play in, keep the classes roughly the same size (100+ images each), and give `nothing` lots of variety — sitting closer or farther, hands resting, hands moving without a gesture.

## Files
- `index.html` — the whole game in one file
