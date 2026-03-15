

## Plan: Update Declarations Slide with Team Members

### Changes to `public/presentation.html`

**1. Update CSS** — Add styles for team member cards with circular photos and student IDs.

**2. Update Declarations slide content** — Replace the `[Name 1-4]` placeholders with a redesigned 4-column layout featuring:
- Circular profile photos for each member
- Names: Krish, Jakub, Christian, Francisco
- Student IDs: s252788, s253074, s196354, s252990
- Updated contribution descriptions matching the user's allocation:
  - **Krish** — Intro, overview & motivation
  - **Jakub** — CBS vs PBS comparison
  - **Christian** — LNS & neural architecture
  - **Francisco** — Results, experiments & critical analysis

**3. Copy uploaded photos to `public/`**:
- `image-3.png` → `public/photos/krish.png`
- `image-4.png` → `public/photos/jakub.png`
- `image.png` → `public/photos/christian.png`
- `image-2.png` → `public/photos/francisco.png`

The declarations slide glass card will be widened (`max-width: 900px`) to fit 4 photo cards side by side, each with a circular clipped image, name in cyan, student ID in dim text, and contribution description below.

