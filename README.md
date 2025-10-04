# Studio Zero Starter Kit

A reusable **Astro + Tailwind v4** starter for client websites.  
Includes: base layout, header, footer, hero, section, card components, config system, SEO/OG tags, and Studio Zero utility classes.

---

## 🚀 Getting Started

### 1. Clone the Repo
```bash
git clone git@github.com:<your-username>/studiozero-starter-kit.git
cd studiozero-starter-kit
npm install
npm run dev
````

Dev server runs at [http://localhost:4321](http://localhost:4321).

---

### 2. Create a New Template

When building a new site/template from the starter:

```bash
cd ../templates
cp -R studiozero-starter-kit studiozero-template-<name>
cd studiozero-template-<name>
rm -rf .git
git init
git add -A
git commit -m "chore: scaffold from starter kit"
git remote add origin git@github.com:<your-username>/studiozero-template-<name>.git
git push -u origin main
```

Each template repo stays clean and independent.

---

## 🎨 Theme & Branding

### Fonts & Colors

* Defined in **`src/styles/global.css`** using Tailwind v4 `@theme` tokens:

  ```css
  @theme {
    --color-primary: #1E40AF;   /* Indigo */
    --color-secondary: #F59E0B; /* Amber */
    --color-accent: #10B981;    /* Emerald */
    --font-heading: "Inter", sans-serif;
    --font-body: "Open Sans", sans-serif;
  }
  ```
* Use in templates:

  ```html
  <h1 class="font-heading text-primary">Hello</h1>
  <p class="font-body text-secondary">Welcome to Studio Zero</p>
  ```

Update tokens here → propagates site-wide.

### Company Info

* Stored in **`src/config/site.ts`**:

  ```ts
  export const siteConfig = {
    companyName: "Studio Zero",
    email: "info@studiozerolab.com",
    phone: "(555) 123-4567",
    socials: {
      instagram: "",
      twitter: "",
      facebook: ""
    }
  };
  ```
* Used throughout site:

  ```astro
  <a href={`mailto:${siteConfig.email}`}>{siteConfig.email}</a>
  ```

Update once → reflected everywhere.

---

## 📦 Components

Core modules included:

* **BaseLayout.astro** → global wrapper (Header, Footer, SEOHead, slot for content)
* **Header.astro** → logo/company name + nav links
* **Footer.astro** → © + Studio Zero credit
* **Hero.astro** → headline, subtitle, CTA button
* **Section.astro** → flexible text/image block
* **Card.astro** → service/package card
* **SEOHead.astro** → `<title>`, `<meta>`, OG tags

---

## 🛠 Utilities

In `src/styles/global.css`, reusable utility classes:

* `.std-container` → max-width container with padding
* `.std-card` → bordered, rounded, shadow card
* `.std-btn` → branded button style
* `.std-grid` → generic grid gap
* `.std-grid--smart` → responsive grid (1–3 cols)
* `.std-grid--fixed` → fixed 3-column grid

---

## 📑 Workflow

1. **Start from starter kit** → copy into new repo.
2. **Update tokens** → edit `global.css` `@theme` block for colors & fonts.
3. **Update company info** → edit `site.ts` once for name, email, phone.
4. **Swap assets** → replace `/src/assets/logo.svg` and placeholders.
5. **Build pages** → import and arrange Hero, Section, Card, etc.
6. **Deploy to Netlify** →

   * Build command: `npm run build`
   * Publish directory: `dist`

---

## ⚡ Notes

* Built on **Astro + Tailwind v4**.
* **VS Code project settings** in `.vscode/` ensure formatting and Tailwind IntelliSense.
* `.editorconfig` keeps spacing/line endings consistent even outside VS Code.
* Ready to extend with optional modules: Gallery, Carousel, Contact Form, Pricing Table, Blog, etc.

```

---
