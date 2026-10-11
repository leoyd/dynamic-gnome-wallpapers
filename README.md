> [!WARNING]
> This repository is currently unmaintained due to lack of free time. Apologies for this.
> There are some major tasks pending for this repository for which I would love some support.

- [ ] Migrating away to a more stable CDN - Right now I am using free version of Oracle Cloud, which is not exactly reliable. I am aiming to move the files to somewhere stable like Amazon S3 or GCS.
- [ ] Supporting GNOME 40 and above - I have not tested the files on Distros with GNOME 40 and above.
- [ ] Adding more wallpapers.

---

<h1 align="center">Dynamic Gnome Wallpapers</h1>
<h6 align="center">A collection of awesome dynamic wallpapers for Gnome, and easy scripts to install them</h6>
<p align="center">
<img src="https://user-images.githubusercontent.com/54291836/130308064-3b82d8c5-2ccf-4351-ae35-6b197daee3f1.gif">
</p>


---

### Original Inspiration
[b1izzard-34/Dynamic-gnome-wallpapers](https://github.com/b1izzard-34/Dynamic-gnome-wallpapers)

## Pre-requisites
- Gnome shell installation
- `unzip` and `curl` commands available

## Wallpaper format
### Every wallpaper zip contains :
- JPEG/JPG files of the wallpaper.
- XML file containing transition information of the wallpaper.
- XML file that adds the wallpaper entry to the gnome backgrounds menu in the control center.

## GNOME Extension (GNOME 47 – 51)

The `extension/` folder contains a GNOME Shell extension that wraps everything below in a graphical interface:

- **Wallpapers page**: install any wallpaper of the gallery with one click, apply or remove installed dynamic wallpapers.
- **Create page**: drop any image and turn it into a dynamic wallpaper. Each variant is a copy of the image with its own color tone (brightness, contrast, saturation, tint color and strength) shown at a given hour. Preview each variant, or simulate a whole day with transitions, before generating it.
- **Panel menu**: quickly switch between installed dynamic wallpapers.

The interface is available in English and French (follows the system language).

### Installing the extension

Requirements:
- GNOME Shell 47 to 51
- `make`, `gettext` (`msgfmt`) and `gnome-extensions` (shipped with GNOME Shell)
- `unzip`, to install wallpapers from the catalog

```bash
git clone https://github.com/leoyd/dynamic-gnome-wallpapers.git
cd dynamic-gnome-wallpapers
make install   # packs and installs the extension for the current user
```

Then enable it:
- **Wayland**: log out and back in first (GNOME Shell only detects new extensions at login).
- **X11**: you can instead restart GNOME Shell with <kbd>Alt</kbd>+<kbd>F2</kbd>, `r`, <kbd>Enter</kbd>.

```bash
gnome-extensions enable dynamic-gnome-wallpapers@leoyd.github.io
```

You can also enable it from the **Extensions** app. To update, pull the latest changes and run `make install` again (then log out and back in on Wayland).

To remove the extension (installed wallpapers are kept):

```bash
make uninstall
```

### Using the extension

Click the wallpaper icon in the top bar:
- the installed dynamic wallpapers are listed, the active one is checked — click one to apply it;
- **Manage and Create Wallpapers…** opens the preferences window (also reachable with `make prefs` or from the Extensions app).

The preferences window has two pages.

**Wallpapers**
- *Installed*: your dynamic wallpapers (user and system ones). **Apply** sets one as the current wallpaper, **Edit** (wallpapers made with the *Create* page) reopens it in the *Create* page with its image and settings, **Remove** deletes its images and files (user wallpapers only; system ones installed with `--global` must be removed with `uninstall.sh`).
- *Catalog*: the ready-made wallpapers of the [gallery](#wallpaper-gallery). **Install** downloads and installs one in `~/.local/share` (same as `install.sh`).

**Create**
1. Drop an image on the *Source Image* area, or click **Choose an Image…** (JPEG, PNG, WebP… the original resolution is kept).
2. In *Variants*, select a variant to edit it: its name, the **hour** at which it is fully shown, and its tone (brightness, contrast, saturation, tint color and strength). Add or remove variants, or restore the default ones (night, dawn, morning, noon, sunset, dusk).
3. *Preview* shows the selected variant; enable **Simulate a Day** to see the wallpaper at any time of day, transitions included, or press play to run through the whole day.
4. In *Creation*, give the wallpaper a name, set the transition length and click **Create**. With **Apply After Creation** enabled, it becomes your wallpaper right away.

To change a wallpaper you created, click **Edit** next to it on the *Wallpapers* page: its image, variants, name and transition are loaded back in the *Create* page. Adjust anything (you can even drop another image), then click **Save Changes** — renaming it replaces the old one. Click **New Wallpaper** in the banner to leave edit mode. The source image and settings are kept in `project.json` next to the frames; wallpapers created before this feature can't be edited.

A variant is fully visible at its hour, stays static, then fades into the next one, finishing at the next variant's hour (the fade is capped by the gap between the two hours).

Wallpapers installed or created by the extension use the same layout as the install script (`~/.local/share/backgrounds/gnome/<code>-timed/`), so they also show up in GNOME Settings › Background and can be removed with `uninstall.sh`.

## Installation

> Replace **THEME_CODE** with the theme code of your choice.

```bash
curl -s https://wallpapers.manishk.dev/install.sh | bash -s THEME_CODE
```

#### Go to Gnome Settings > Backgrounds and set your wallpaper from there

### Uninstallation
If you have installed a Wallpaper and want to uninstall it

> Replace **THEME_CODE** with the code of the theme you want to uninstall

```bash
curl -s https://wallpapers.manishk.dev/uninstall.sh | bash -s THEME_CODE
```

### Global Installation (Optional)
If you want to install a wallpaper for all users on your system, you can run the same command using sudo and by passing the `--global` flag

```bash
curl -s https://wallpapers.manishk.dev/install.sh | sudo bash -s THEME_CODE --global
```

To uninstall a globally installed wallpaper

```bash
curl -s https://wallpapers.manishk.dev/uninstall.sh | sudo bash -s THEME_CODE --global
```
---
## Wallpaper Gallery

### Lakeside

#### **Code**: `Lakeside`

![Lakeside](https://user-images.githubusercontent.com/54291836/126888360-48c90397-49fb-44ed-af52-f793178e1f63.gif)

#### Credits

https://dribbble.com/shots/1816328-Lakeside-Sunrise

---

### A Certain Magical Index

#### **Code**: `A_Certain_Magical_Index`

> This specific wallpaper is more than **500 MB** in download size, so install only if you have that bandwidth available

![A Certain Magical Index](https://user-images.githubusercontent.com/54291836/126893468-8ac4590e-ceea-40a2-a938-3e4db0f6ddf9.gif)

#### Credits

https://dynamicwallpaper.club/u/legend

---

### Exodus

#### **Code**: `Exodus`

![Exodus](https://user-images.githubusercontent.com/54291836/126888357-3dfde85b-b371-4d41-9695-d569c1424a48.gif)

#### Credits
https://dynamicwallpaper.club/u/Juanra

---
### Minimal Mojave

#### **Code**: `Minimal-Mojave`

![Minimal-Mojave](https://user-images.githubusercontent.com/54291836/126888359-de35b414-cc69-494b-8065-487de5f22924.gif)

#### Credits
https://dynamicwallpaper.club/u/octaviotti

---

### Mojave

#### **Code**: `Mojave`

![Mojave](https://user-images.githubusercontent.com/54291836/126888358-ac91b4f6-0685-4fd3-8928-db4eebc75434.gif)

#### Credits

https://www.reddit.com/r/apple/comments/8oz25c/all_16_full_resolution_macos_mojave_dynamic/

---

### Mojave V2

#### **Code**: `MojaveV2`

![MojaveV2](https://user-images.githubusercontent.com/54291836/126888353-e1eec7c1-f5c0-48cf-b4dd-c987e11b9b69.gif)

#### Credits

https://dynamicwallpaper.club/u/WeighingDog

---

### Big Sur Beach

#### **Code**: `Big_Sur_Beach`

![Big_Sur_Beach](https://user-images.githubusercontent.com/54291836/126888350-d954464c-5838-40d6-a585-5c622f1e22c8.gif)

#### Credits

https://dynamicwallpaper.club/u/DavidPicnic

---

### Firewatch
#### **Code**: `Firewatch`

![Firewatch](https://user-images.githubusercontent.com/54291836/126888351-023dbd48-7a49-442b-b909-91f995ed749e.gif)

#### Credits

https://dynamicwallpaper.club/u/Jagoba

---

### Lakeside 2

#### **Code**: `Lakeside-2`

![Lakeside-2](https://user-images.githubusercontent.com/54291836/126888345-10183721-0984-40c3-82bf-20c147897c6c.gif)

#### Credits
https://dynamicwallpaper.club/u/vitaobr92

---

### Big Sur

#### **Code**: `Big_Sur`

![Big Sur](https://user-images.githubusercontent.com/54291836/127216821-83a15fe9-ebf3-4e8a-ae98-49dc9f4b792b.gif)

#### Credits

https://dynamicwallpaper.club/u/jalbans17

---

### Fuji

#### **Code**: `Fuji`

![Fuji](https://user-images.githubusercontent.com/54291836/127258707-7895e748-ddc8-4e06-8767-df7609e834bd.gif)

#### Credits

https://dynamicwallpaper.club/u/MaxKulakov

---
### Catalina

#### **Code**: `Catalina`
![Catalina](https://user-images.githubusercontent.com/54291836/130307589-cfae49ee-8199-4da1-a505-4a3947ef0663.gif)

#### Credits
https://dynamicwallpaper.club/u/wallpapyrus

---

### Contributors

<a href = "https://github.com/manishprivet/dynamic-gnome-wallpapers/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=manishprivet/dynamic-gnome-wallpapers"/>
</a>

---
## Reach me out

<a href="https://manishk.dev" target="blank">Website</a> |  <a href="https://twitter.com/manishprivet" target="blank">Twitter</a> |  <a href="https://linkedin.com/in/manishprivet" target="blank">Linkedin</a> |  <a href="https://stackoverflow.com/users/manishprivet" target="blank">Stackoverflow</a> |  <a href="https://fb.com/manishprivet" target="blank">Facebook</a> |  <a href="https://instagram.com/manishprivet" target="blank">Instagram</a> |  <a href="https://medium.com/@manishprivet" target="blank">Medium</a>
