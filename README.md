# Robot Township

A Python + Pygame township-building sim: solve puzzles, earn coins and XP,
build an unlimited scrolling township, farm crops, assemble a robot, and
grow your population and happiness.

Play it in the browser (once GitHub Pages is set up below), or run it
locally with Python.

## Play locally

```bash
pip install -r requirements.txt
python township_game_1.py
```

Controls: arrow keys or the on-screen ◄►▲▼ arrows pan the camera,
left-click to build/interact, right-click a building to demolish it.

## Play in the browser / host on GitHub Pages

This repo already includes a GitHub Actions workflow
(`.github/workflows/deploy.yml`) that automatically builds the browser
(WebAssembly) version with [pygbag](https://github.com/pygame-web/pygbag)
and publishes it to GitHub Pages every time you push to `main`. To turn it
on:

1. Create a new GitHub repository and push this folder to it:
   ```bash
   git init
   git add .
   git commit -m "Robot Township"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
2. On GitHub, go to **Settings → Pages**, and under **Build and
   deployment → Source**, choose **GitHub Actions**.
3. Push again (or re-run the workflow from the **Actions** tab). The
   build takes a minute or two.
4. Your game will be live at:
   `https://<your-username>.github.io/<your-repo>/`

You don't need to install pygbag yourself - the workflow does the build
for you in the cloud on every push.

## Building the web version yourself (optional)

If you want to test the browser build locally before pushing:

```bash
pip install pygbag
python -m pygbag township_game_1.py
```

This serves the game at `http://localhost:8000`. The static files end up
in `build/web/`, which is exactly what the GitHub Action publishes.
