# Virtual Try-On Demo

Single-page static gallery for a founder pitch. Pre-rendered CatVTON results; the page mimics a live try-on experience.

## How to add a new look

1. Create a folder under `images/` (e.g. `images/pair_07/`) and add three files:
   - `person.jpg` — the person input photo
   - `garment.jpg` — the garment input photo
   - `result.jpg` — the CatVTON output

2. Open `index.html` and append one object to the `looks` array at the bottom of the file:

   ```javascript
   {
     id: 'pair_07',
     person: 'images/pair_07/person.jpg',
     garment: 'images/pair_07/garment.jpg',
     result: 'images/pair_07/result.jpg',
     caption: 'Your caption here',
   },
   ```

3. Open `index.html` in a browser (or refresh if already open). The new card appears automatically.

To remove a look, delete its folder and remove its entry from the `looks` array.

## How to deploy

From the `vto-demo/` directory:

```bash
git init
git add index.html images/ README.md .gitignore
git commit -m "Add virtual try-on demo gallery"
```

Create a repo on GitHub, then:

```bash
git remote add origin https://github.com/yourusername/your-repo.git
git branch -M main
git push -u origin main
```

On [vercel.com](https://vercel.com): **Add New Project** → import the repo → leave framework preset as **Other** (no build command) → deploy. Vercel serves `index.html` at the root.

Alternatively, with the Vercel CLI:

```bash
npm i -g vercel
vercel
```

Follow the prompts. No build step required.

## Local preview

Double-click `index.html`, or serve the folder for reliable image loading:

```bash
python -m http.server 8080
```

Open `http://localhost:8080`.
