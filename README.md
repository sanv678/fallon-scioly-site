# Fallon Science Olympiad — Website

A 4-page site for the Fallon Science Olympiad team.

## Files

```
index.html       Home / About Fallon Science Olympiad
join.html        How to Join (3-step process + expectations)
coaches.html     Meet the Coaches (placeholders for both bios + photos)
archive.html     2025-26 photo gallery
styles.css       Shared stylesheet (Science Olympiad navy + gold colors)
images/          Folder for all photos
```

To preview the site, just double-click `index.html` and it will open in your browser. All four pages link to each other.

---

## What you still need to fill in

There are three sets of placeholders to replace:

### 1. The info meeting date (in `join.html`)
Find this block and replace the bracketed text:
```
[ DATE / TIME / LOCATION GOES HERE ]
```

### 2. Coach bios + photos (in `coaches.html`)
Two coach cards near the top. Each has:
- `[ Coach 1 Full Name ]` / `[ Coach 2 Full Name ]`
- `[ Grade / School ]`
- `[ Favorite Events ]`
- `[ About — short bio ]`
- `[ Why I Coach ]`

For each coach photo, save your photo into the `images/` folder as `coach1.jpg` and `coach2.jpg`. Then in `coaches.html`, find the comment that says `<!-- To add a real photo, replace this whole div with: ... -->` and follow that instruction.

### 3. Official Science Olympiad logo
The site already has logo slots wired up in the home-page hero and in every footer. To activate them:

- Save the official Science Olympiad logo as `images/scioly_logo.png`
- That's it — the badge will appear automatically on all 4 pages
- If the file is missing, the badge text hides on its own (so it never looks broken)

### 4. Archive photos (in `archive.html`, also `index.html`)
Each photo placeholder shows a suggested filename. Save your photo into the `images/` folder using that filename, then swap the placeholder.

**Example — replacing a placeholder:**

Find this block:
```html
<div class="gallery-item">
  <div class="gallery-placeholder">
    <span class="icon">📸</span>
    <span class="label">team_group_photo.jpg</span>
  </div>
</div>
```

Replace it with:
```html
<div class="gallery-item">
  <img src="images/team_group_photo.jpg" alt="The 2025-26 Fallon Science Olympiad team" />
</div>
```

That's it!

---

## About the photos in this version

You shared a WhatsApp video that contained one event (the Wright Stuff testing). I extracted a still from it and used it as `images/wright_stuff.jpg` — so that one slot is already filled with a real team photo.

The other 9 photos you shared visually didn't come through as actual image files I could save. **To add them**, save each photo onto your computer and drop them into the `images/` folder. Suggested filenames (matching what's already wired into the site):

- `team_group_photo.jpg` — the full team photo with the red banner
- `mission_possible_outdoor.jpg` — 4 girls outside with the pegboard
- `mission_possible_thecave.jpg` — 2 girls in front of the "Mission Possible" sign
- `chem_lab.jpg` — student in lab coat doing chemistry
- `lab_coats_pair.jpg` — two students in lab coats outside
- `lab_goggles.jpg` — student with goggles testing the pegboard
- `scrambler_or_wagon.jpg` — three students around the wagon
- `circuit_lab.jpg` — two boys with multimeters

**Practice / build session photos** (used on home + coaches + archive):
- `home_build_pair.jpg` — two girls measuring at the dining table
- `home_chem_pair.jpg` — two girls testing a clear plastic device
- `home_build_trio.jpg` — three students at the table working on a build
- `vehicle_test.jpg` — hallway scrambler/vehicle testing
- `flight_test.jpg` — helicopter / parachute drop test

You can rename them however you want — just make sure the filename in the HTML matches.

---

## Hosting the site

The site is plain HTML/CSS — no build step needed. Easy free hosting options:

- **GitHub Pages** — free, perfect for school projects. Create a repo, upload these files, enable Pages in settings.
- **Netlify** — drag-and-drop the folder onto netlify.com/drop, get a free URL.
- **Google Sites** — if you want zero technical work, you can also rebuild this in Google Sites for free.

---

## Colors used

- Navy: `#002855` (primary)
- Gold: `#f5b800` (accent)
- White / off-white background

If you want to switch to your school's colors, edit the `:root` block at the top of `styles.css`.
