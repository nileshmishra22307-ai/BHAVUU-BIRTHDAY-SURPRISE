# A Little Universe — Birthday Treasure Hunt

A romantic, mobile-first birthday website built with plain HTML, CSS and JavaScript. It can be hosted free with GitHub Pages.

## 1. Before you publish

1. Open `script.js`.
2. Find `SETTINGS.password` and replace `DDMMYYYY` with your chosen date in the exact format you want, e.g. `14022025`. This is only an example—use your own date.
3. Personalize `SETTINGS.finalLetter`.
4. In the `GIFTS` list in `script.js`, edit the gift clues, hints, accepted answers, messages, and real-life clues.
5. Add your own photos and audio files using the names below.

**Important privacy note:** This is a surprise gate, not secure authentication. The password and accepted answers are in JavaScript and can be inspected by visitors. GitHub Pages is static hosting. Anyone with the public URL may be able to access public assets. Don't upload anything you truly need to keep private.

## 2. Add photos

Put your files inside `assets/images/` and use these exact filenames:

- `her-photo.jpg` — main birthday portrait
- `memory-1.jpg` and `memory-2.jpg` — shared memories
- `jhumka.jpg`
- `ring-1.jpg`
- `ring-2.jpg`
- `lip-tint.jpg`
- `watch.jpg`
- `hand-cuff-bracelet.jpg`
- `chocolate-gift-card.jpg`
- `final-photo.jpg` — optional finale photo

JPG or WebP is recommended. Keep images reasonably compressed (roughly 200–600 KB each when possible). You can use PNG too, but then update the filename in the relevant HTML/JS path. Use only photos you have permission to share.

## 3. Add music and sound effects

Place audio files inside `assets/audio/`:

- `birthday-song.mp3`
- `soft-instrumental.mp3`
- `unlock.mp3`
- `wrong-answer.mp3`
- `reveal-1.mp3` through `reveal-7.mp3`
- `finale.mp3`
- `voice-note.mp3` (optional)

Audio is optional. If a file doesn't exist, the browser will simply fail to play that sound; the site still works. Use music you have permission to use. Browsers usually require a user interaction before playing audio.

To remove music entirely, set `musicEnabled: false` in `SETTINGS`.

## 4. Test on your laptop

Open `index.html` in a modern browser. For a more realistic test, use VS Code's Live Server extension, or run a local server from the project folder:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`. Stop the server with Ctrl+C.

Test:
- Wrong password does not advance.
- Correct password opens the birthday scene.
- Each wrong puzzle answer stays locked.
- Correct answer reveals only the current gift.
- The next gift is only reachable via the next button.
- All seven gifts lead to the final letter.
- Test on a phone-sized browser and on an actual phone after publishing.

## 5. Publish using GitHub Pages

1. Sign in at https://github.com/
2. Create a new repository, e.g. `birthday-treasure-hunt`.
3. For the easiest free GitHub Pages setup, make the repository **Public**.
4. Upload `index.html`, `style.css`, `script.js`, `README.md`, and the `assets` folder with its contents to the repository root. Do not upload only the ZIP.
5. Open the repository's **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**.
7. Choose branch `main` and folder `/(root)`, then save.
8. Wait for the deployment to finish. GitHub will show the published URL in Settings → Pages. It commonly looks like `https://YOUR-USERNAME.github.io/birthday-treasure-hunt/`.
9. Open that exact URL on your phone. Check images, music, puzzles, and the final scene.

After changing any file, commit the changes and wait for Pages to redeploy.

## 6. How to change a puzzle answer

In `script.js`, find a gift object in the `GIFTS` array. For example:

```js
answers: ["jhumka", "झुमका", "earring", "earrings"],
```

Add other acceptable spellings inside the square brackets. The answer check ignores capitalization and punctuation by default.

## 7. Troubleshooting

- **Password never works:** replace `DDMMYYYY` in `SETTINGS.password` with your exact chosen password.
- **Photo placeholder appears:** confirm the filename and path match exactly; filenames are case-sensitive on GitHub Pages.
- **Music does not play:** tap the music button, verify the MP3 exists, and use a browser-supported audio file.
- **404 page:** check that `index.html` is at the repository root and Pages is configured to `main` / `/(root)`.
- **Old version appears:** wait a minute, refresh, or hard-refresh with Ctrl+F5.
- **Answer seems right but won't work:** add its spelling to that gift's `answers` list.

## 8. Before sharing

- Replace the password placeholder.
- Replace the sample final letter with your own words.
- Replace all photos and edit all physical gift clues.
- Test every correct and incorrect answer.
- Remember that a public site and its assets are not private. Avoid putting private information or sensitive images on it.


## Readability and personalization update

The updated stylesheet increases text sizes and touch targets for easier mobile use. The chocolate gift reveal now adds animated `😂 🍫 🤪` emojis. The final letter in `SETTINGS.finalLetter` has been expanded and can be personalized. Replace the updated `style.css`, `script.js`, and `README.md` in your GitHub repository, commit the changes, then refresh the Pages URL after deployment.


## Audio flow in this update
- `birthday-song.mp3`: plays on the birthday welcome slide.
- `soft-instrumental.mp3`: takes over when the memories/treasure section begins and loops during the hunt.
- `reveal-1.mp3` through `reveal-7.mp3`: individual gift-reveal sound effects; they pause the background track while the effect plays.
- `finale.mp3`: plays by itself when the final letter opens, without looping or restarting another track afterward.
- `voice-note.mp3`: starting the voice note stops all other audio; after the voice note ends, the page stays silent.
- Photo frames are larger and use `object-fit: contain` so the full image is visible rather than being cropped. If a photo has a different aspect ratio, empty space may appear around it instead of cutting off the photo.


## Interactive task mode
Each gift now unlocks only after a small interactive task:
1. Choose a birthday mood.
2. Write a little shared-memory note.
3. Tap all three hearts in the mini-game.
4. Choose a lip-tint style.
5. Describe your ideal day together.
6. Write a little promise.
7. Type the final phrase: `I AM THE TREASURE HUNT CHAMPION`.

Choice tasks accept any option; text tasks require an answer; the final phrase is checked. This is a playful client-side challenge, not secure authentication—answers and code can be inspected in the public repository.


## Updated flow: task → guess the gift → reveal
The player first completes the task. Only then does the website show a separate field asking what gift she thinks it might be. The gift photo and name are revealed only after an accepted guess. A wrong guess can be retried. After reveal, the next task starts; no real-world gift hiding place is required.


## Real-life task → passkey → gift guess flow

Each gift now follows this order:
1. She completes the real-life task shown on the page.
2. She taps **Task complete ho gaya**.
3. She asks you for the passkey; you tell her the passkey in person.
4. She enters the passkey to move to the gift-guess page.
5. The website reveals the gift only when she guesses correctly.

### Passkeys you give her
Edit the `passkey` values for each item in `script.js` if you want different passkeys:
- Gift 1: `MOON01`
- Gift 2: `PINKY02`
- Gift 3: `SPARK03`
- Gift 4: `BLUSH04`
- Gift 5: `TIME05`
- Gift 6: `TOGETHER06`
- Gift 7: `SWEET07`

These passkeys are only a playful gate, not secure authentication; the values are visible in the site's public JavaScript source. Gift guesses are intentionally the only answer that reveals each gift. The site does not show a direct gift hint.


### Gift guess choice
On the gift guess page, she can type the correct gift name to unlock it, or press **No** to reveal the surprise without guessing.


### Personal-memory passkey clues
The passkey page now shows an indirect, romantic memory prompt for each stage:
1. Where you first met.
2. The first thing you brought into her life.
3. Where you sat alone together on her birthday for the first time.
4. Your first café.
5. Where you were returning from when you first got caught in the rain together.
6. Your favourite movie genre.
7. The last movie you watched together on a phone.

These prompts are intentionally indirect. Enter the real passkey answers you choose in the `passkey` fields in `script.js`; the clue text itself is not the answer.
