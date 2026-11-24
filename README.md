# digital-signage

Slide images for the digital-signage / kiosk TV screens in School of Science
buildings. Each folder holds the slides shown in one building. To add a slide,
copy the image into every building folder where it should appear and commit.
To remove a slide, delete it from that folder.

## Standard slide sizes

| Folder | Building | Orientation | Slide size | Aspect |
|--------|----------|-------------|------------|--------|
| `b15/` | Building 15 | **Portrait** | **1080 × 1920 px** | 9:16 |
| `b18/` | Building 18 | **Landscape** | **1920 × 1080 px** | 16:9 |
| `b19/` | Building 19 | **Landscape** | **1920 × 1080 px** | 16:9 |
| `b23/` | Building 23 | **Landscape** | **1920 × 1080 px** | 16:9 |

B15 is portrait and the other buildings are landscape. A slide meant for every
building therefore needs **two versions**. Add `_Landscape` / `_Portrait` to
the file names, for example `PeerLeadership_Landscape.png`. Don't drop a 16:9
slide into `b15/`, because it will show as a thin strip across the middle of
the screen. Re-lay the content vertically instead.

4K exports (3840 × 2160 or 2160 × 3840) also work. Anything larger only makes
the file bigger.

### Safe area

Players can crop or letterbox slides slightly, and some show content in a frame
a little wider or narrower than the standard. Keep all text, logos and QR codes
inside the safe area:

| Orientation | Safe area | Margins |
|-------------|-----------|---------|
| Landscape (1920 × 1080) | centre 1800 × 900 px | 60 px at the sides, 90 px top and bottom |
| Portrait (1080 × 1920) | centre 960 × 1720 px | 60 px at the sides, 100 px top and bottom |

Backgrounds and photos should still fill the whole canvas, all the way to the
edges.

### File format

- **PNG** is for slides that are mostly text, logos, QR codes, charts or flat
  colour. It keeps edges sharp.
- **JPG** at 80–90% quality is for photo-heavy slides. It is much smaller than
  PNG for photos.
- Use **RGB** colour (sRGB) with **no transparency**. Transparent areas can
  show up black or white on the player.
- Aim for **under 2 MB per file**. Large files slow syncing and look no better
  on screen. If a PNG is big, it usually contains a photo, so export it as JPG.
- Don't use PDF, PPTX, GIF, WebP or video files. Export a still image for each
  slide.
- **Name files after their content**, for example `NSSS26.png` or
  `CampusSecurity.jpg`, not `Slide1.PNG`. Generic names make it hard to tell
  later what to update or remove.

---

## Exporting slides

Set the slide size **before** you start designing. Changing it afterwards
stretches or reflows the content.

### PowerPoint on Windows

1. **Set the slide size.** Go to *Design → Slide Size*:
   - **Landscape:** choose *Widescreen (16:9)*.
   - **Portrait (B15):** choose *Custom Slide Size*, set Width **19.05 cm**
     (7.5 in) and Height **33.867 cm** (13.333 in), then click *OK* and
     *Ensure Fit*.
2. **Export.** Go to *File → Export → Change File Type*, choose *PNG Portable
   Network Graphics* (or *JPEG File Interchange Format* for photo-heavy
   slides), and click *Save As*. When prompted, choose *All Slides* or
   *Just This One*.
3. **Check the size.** PowerPoint for Windows exports at 96 dpi by default,
   which gives **1280 × 720**, not 1920 × 1080. If you get that size, either:
   - **Resize the export** to 1920 × 1080 (see *Checking and fixing images*
     below). This is fine for simple slides. Or:
   - **Change the export resolution permanently.** Close PowerPoint and open
     *Registry Editor* (`regedit`). Go to
     `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\PowerPoint\Options`
     and add a *DWORD (32-bit) Value* named `ExportBitmapResolution` with
     decimal value **144**. Exports will then be 1920 × 1080 (or 1080 × 1920
     for portrait). You may need IT approval to edit the registry.

### PowerPoint on macOS

1. **Set the slide size.** Go to *Design → Slide Size*:
   - **Landscape:** choose *Widescreen (16:9)*.
   - **Portrait (B15):** choose *Page Setup*, set Width **19.05 cm** and
     Height **33.867 cm**, then choose *Portrait* orientation and *Scale*.
2. **Export.** Go to *File → Export*:
   - **File Format:** *PNG* (or *JPEG* for photo-heavy slides).
   - **Scope:** *Save Every Slide* or *Save Current Slide Only*.
   - **Width × Height:** type **1920 × 1080** (or **1080 × 1920** for
     portrait).
3. **Save the export.** Click *Export*. When exporting every slide,
   PowerPoint creates a folder of numbered images. Rename them after their
   content before copying them in.

### Keynote (macOS)

1. **Set the slide size.** Click *Document* in the toolbar, then under
   *Slide Size* choose *Custom Slide Size* and enter **1920 × 1080** (or
   **1080 × 1920**).
2. **Export.** Go to *File → Export To → Images*, choose *PNG* (or *JPEG
   (High Quality)*), select *All* or a range of slides, then click *Next*.
   Keynote exports at the slide's pixel size.

### Canva (browser, Windows or macOS)

1. **Set the design size.** Go to *Create a design → Custom size* and enter
   **1920 × 1080 px** (or **1080 × 1920 px**).
2. **Download.** Go to *Share → Download*, choose *PNG* (or *JPG* for
   photo-heavy slides), keep the size at 1×, choose the pages you want, and
   click *Download*. Multiple pages download as a `.zip`. Extract it first.

---

## Checking and fixing images

### Check the pixel size

- **Windows:** right-click the file, choose *Properties*, open the *Details*
  tab and look under *Image → Dimensions*. Or hover over the file in File
  Explorer.
- **macOS:** select the file in Finder, press **⌘I** (Get Info), and look
  under *More Info → Dimensions*. Or open it in Preview and choose *Tools →
  Show Inspector*.

### Resize an image

Only resize when the image is already the right shape (16:9 or 9:16).
Otherwise it will stretch. Fix the slide size at the source and re-export
instead.

- **Windows (Photos app):** open the image, click *… → Resize image*, choose
  *Define custom dimensions*, set the width to 1920 (or 1080) with *Maintain
  aspect ratio* ticked, and save as a copy.
- **Windows (Paint):** go to *Home → Resize*, choose *Pixels*, enter the
  width with *Maintain aspect ratio* ticked, then use *File → Save as*.
- **macOS (Preview):** go to *Tools → Adjust Size*, set the units to
  *pixels*, enter the width with *Scale proportionally* ticked, then use
  *File → Save*.

### Convert PNG to JPG (to shrink photo-heavy files)

- **Windows (Paint):** open the PNG, go to *File → Save as → JPEG picture*.
- **macOS (Preview):** open the PNG, go to *File → Export*, choose *JPEG*,
  and set the *Quality* slider to around 80%.

---

## Pre-publish checklist

- [ ] Correct orientation and pixel size for each building folder (portrait
      for B15)
- [ ] Text, logos and QR codes are inside the safe area
- [ ] PNG or JPG, RGB, no transparency, under about 2 MB
- [ ] Descriptive file name, copied into every relevant building folder
- [ ] Expired slides removed
