# Google Drive Video Embedding Support & Portfolio Section

## Problem Description

### Part 1: Video Embedding (COMPLETED)

The Hugo-Porto template didn't support embedding videos from Google Drive. Google Drive video embeds require iframe HTML tags, which are blocked by Hugo's default Goldmark renderer safety settings.

**Status**: ✅ Completed

- Unsafe HTML rendering enabled in `hugo.toml`
- Custom `gdrive-video` shortcode created
- Documentation added

### Part 2: Portfolio Video Grid Section (COMPLETED)

The site needs a dedicated portfolio section on the landing page to showcase video work with a grid layout and modal dialog interface.

## Proposed Solution - Portfolio Section

Create a new "portfolios" section with:

1. 3-column responsive grid layout (1 col mobile, 2 cols tablet, 3 cols desktop)
2. Video thumbnail cards with play button overlay
3. Modal dialog for video playback
4. Google Drive thumbnail auto-generation
5. Optional custom thumbnail support

## Implementation Design - Portfolio Section

### 1. Install Swiper.js

Add Swiper CSS and JS to the theme:

- Download Swiper.js bundle to `static/js/swiper-bundle.min.js`
- Download Swiper CSS to `static/css/swiper-bundle.min.css`
- Create custom partial to include Swiper assets

### 2. Portfolio Data Configuration

Create `data/sections/portfolios.toml`:

```toml
title = "Video Portfolio"

[[portfolio]]
  title = "Project Title"
  description = "Brief description"
  gdrive_id = "YOUR_FILE_ID"

[[portfolio]]
  title = "Another Project"
  description = "Description here"
  gdrive_id = "YOUR_FILE_ID"
```

### 3. Portfolio Section Template

Create `layouts/partials/sections/portfolios.html`:

- Swiper carousel container
- Loop through portfolio data
- Embed videos using gdrive-video shortcode logic
- Navigation arrows and pagination
- Responsive styling with Tailwind

### 4. Enable Section

Add portfolios section to `data/home.toml`

### 5. Custom Layout Override

Create `layouts/_default/baseof.html` to include Swiper assets

## Testing Plan - Portfolio Section

1. **Swiper Integration**: Verify Swiper.js loads correctly
2. **Data Loading**: Check portfolio data is read from TOML
3. **Carousel Functionality**: Test navigation, autoplay, responsiveness
4. **Build Test**: Run `make build` to ensure no errors
5. **Visual Test**: Test carousel in browser on different screen sizes
6. **Video Loading**: Verify Google Drive videos embed correctly in carousel

## TODO List

### Video Embedding Tasks (COMPLETED)

- [x] Update `hugo.toml` to enable unsafe HTML rendering
- [x] Create `layouts/shortcodes/gdrive-video.html` shortcode
- [x] Add example usage to `content/posts/hello-world/index.md`
- [x] Run build to check for errors
- [x] Test locally with dev server
- [x] Review implementation

### Part 2: Portfolio Grid Section

- [x] Create portfolio data file `data/sections/portfolios.toml`
- [x] Create portfolio section template with grid layout
- [x] Implement modal dialog for video playback
- [x] Add thumbnail support (Google Drive auto + custom)
- [x] Add JavaScript for modal interactions
- [x] Add portfolios section to `data/home.toml`
- [x] Test build and functionality
- [x] Review grid implementation
