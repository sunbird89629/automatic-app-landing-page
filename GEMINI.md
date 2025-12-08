# Gemini Context: Automatic App Landing Page

## Project Overview

This project is a Jekyll-based static website template designed to create landing pages for iOS and Android applications. It is optimized for deployment on GitHub Pages and allows for extensive customization without touching HTML or CSS, primarily through the `_config.yml` file.

**Key Features:**
*   **Automatic Metadata:** Fetches iOS app details (icon, name, price) using the `ios_app_id`.
*   **No-Code Customization:** Most settings (colors, links, features) are managed in `_config.yml`.
*   **Media Support:** Built-in support for app screenshots and video previews within a device frame.
*   **Standard Pages:** Includes templates for Privacy Policy and Changelog.

## Architecture & Technologies

*   **Static Site Generator:** [Jekyll](https://jekyllrb.com/)
*   **Hosting:** [GitHub Pages](https://pages.github.com/)
*   **Styling:** SCSS (`_sass` directory, compiled to `main.css`).
*   **Templating:** Liquid templating engine (files in `_layouts`, `_includes`).

## Key Files & Directories

*   **`_config.yml`**: The central configuration file. This is where the user inputs their app ID, social links, theme colors, and feature list. **This is the primary file for user interaction.**
*   **`Gemfile`**: Defines the Ruby dependencies, specifically the `github-pages` gem which ensures the local environment matches GitHub Pages.
*   **`_includes/`**: Contains reusable HTML snippets like the header (`header.html`), features section (`features.html`), and footer (`footer.html`).
*   **`_layouts/`**: Defines the page templates (`default.html` for the landing page, `page.html` for markdown pages).
*   **`assets/`**: Stores images and videos. Special subdirectories:
    *   `assets/screenshot/`: For the app screenshot (PNG/JPG).
    *   `assets/videos/`: For video previews (MP4/MOV for Safari, WEBM/OGG for Chrome/Firefox).
*   **`_pages/`**: Contains markdown files for auxiliary pages like `privacypolicy.md` and `changelog.md`.

## Setup & Usage

### Local Development

1.  **Install Dependencies:**
    ```bash
    bundle install
    ```

2.  **Run Locally:**
    ```bash
    bundle exec jekyll serve
    ```
    The site will be available at `http://localhost:4000`.

### Configuration (The "How-To")

To customize the site for a specific app, the user should:
1.  **Edit `_config.yml`**:
    *   Set `ios_app_id` to automatically fetch App Store data.
    *   Configure colors, social links, and the feature list.
2.  **Add Assets**:
    *   Place a screenshot in `assets/screenshot/`.
    *   Place video files in `assets/videos/`.
3.  **Update Content**:
    *   Edit `_pages/privacypolicy.md` and `_pages/changelog.md`.

## Common Tasks

*   **Changing the App Icon:** If `ios_app_id` is set, it's automatic. Otherwise, set `app_icon` path in `_config.yml`.
*   **Adding Features:** Add new entries to the `features` list in `_config.yml`.
*   **Changing Colors:** Update the color variables (e.g., `link_color`, `topbar_color`) in `_config.yml`.

## Important Notes

*   **Video Formats:** For broad browser support, both Safari-friendly (`.mp4`/`.mov`) and Chrome/Firefox-friendly (`.webm`/`.ogg`) formats should be provided in `assets/videos/`.
*   **Resolutions:** Assets should ideally match specific device resolutions (e.g., 828x1792, 1125x2436) as noted in the README.
