# Mugeshst007 Profile Setup

This package recreates the reference profile's design architecture using Mugesh's own data. It contains a custom README, locally generated SVG cards and radar charts, plus GitHub Actions for live metrics and the contribution snake.

## 1. Copy the package into your profile repository

Copy everything inside this folder into:

```text
D:\ai project\My profile\Mugeshst007
```

Keep the `.github`, `assets`, and `scripts` folders. They are required; uploading only `README.md` will break the design.

## 2. Optional custom dot-matrix portrait

The README currently uses your live GitHub avatar. To create the reference-style dot-matrix portrait, save your original photo as `assets/profile-photo.png`, install Pillow, and run:

```powershell
pip install pillow
python scripts\dotify.py assets\profile-photo.png -o assets\portrait --cols 100 --equalize --detail 0.5 --color --reveal --circle
```

Then replace this line in `README.md`:

```html
<img src="https://github.com/Mugeshst007.png" width="260" alt="Mugesh ST">
```

with:

```html
<img src="assets/portrait.svg" width="300" alt="Mugesh ST rendered as a dot matrix">
```

## 3. Push the complete package

From your `Mugeshst007` repository folder:

```powershell
git add -A
git commit -m "Build dynamic GitHub profile"
git push
```

## 4. Enable workflow write access

On GitHub, open:

```text
Mugeshst007 repository → Settings → Actions → General → Workflow permissions
```

Select **Read and write permissions**, then save.

## 5. Add the metrics token

1. Open GitHub **Settings → Developer settings → Personal access tokens → Tokens (classic)**.
2. Generate a classic token with `read:user`. Add `repo` only if private repositories should be counted.
3. In the `Mugeshst007` repository, open **Settings → Secrets and variables → Actions**.
4. Create a repository secret named `METRICS_TOKEN` and paste the token.

Never place the token in `README.md` or commit it to the repository.

## 6. Run the workflows

Open the repository's **Actions** tab and run:

1. **Charts and cards**
2. **Metrics**
3. **Snake**

The first run replaces the setup placeholders with your live GitHub data. The snake appears after the `output` branch is created.

## Updating the profile

- Edit `assets/skills.json` to change the self-rated skill radar.
- Edit `assets/projects.json` to change featured repositories.
- The cards and charts refresh automatically on their schedules.
