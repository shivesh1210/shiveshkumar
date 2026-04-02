### 1. About Page

The **About** page involves three files you can modify:

- `about.md` → `/\_pages

  - Contains the main content that appears on the page.

- `about.liquid` → `/_layouts/about.liquid`

  - Controls the page's styling.
  - From here, I commented out `latest_posts` using:
    `{%- comment -%} (text to comment) {%- endcomment -%}`  
    This comments it **only on the About page**. You can do the same for other content.

- `about.markdown` → `/vendor/bundle/ruby/3.2.0/gems/jekyll-4.3.3/lib/site_template

  - No need to modify this file.

Additional notes:

- The site title (`shivesh kumar`) is set in `_config.yml`.
- You can also disable `latest_posts` **site-wide** from `_config.yml` by setting `enabled: false`.

For the **"selected publications"**, there are two options:

1.  **Option 1**: Add `selected = {true}` to the relevant publication in
    `/_bibliography/publication.bib`, and update `selected_paper.liquid` using:
    `<pre> ```liquid <div class="publications"> {% bibliography --query @*[selected=true]* %} </div> ``` </pre>`
2.  **Option 2**: Create a new `selected.bib` inside the `_bibliography` folder and include only the desired publications. Then update `selected_paper.liquid` like so:

    `<pre> ```liquid <div class="publications"> {% bibliography --file selected %} </div> ``` </pre>`

---

### 2. Publications Page

This page uses three main files:

- `publication.md` → `/_pages/`

  - Includes the search box.

- `publication.bib` → `/_bibliography/`

  - Contains all publication entries. You can change their order here.

- `bib.liquid` → `/_layouts/`

  - Defines how each publication entry is styled and what information is shown.

---

### 3. Projects Page

More files are involved here:

- `projects.md` → `/_pages/`
- `projects.liquid` → `/_includes/`
- `_projects/` folder: contains six `.md` files, each representing a project.

---

### 4. Career Page

To add content:

- Use only `career.md`, or create a `career.liquid` file.
- You can also create a `career.yml` file for storing data.

---

### 5. CV Page

- To customize the appearance of sections like **Basics**, **Work**, **Grants**, etc., use `.liquid` files in:
  `/_includes/resume/`
- To edit the actual content, modify `resume.json`:
  `/assets/json/`

To add a **new section**:

1.  Create a `.liquid` file for it.
2.  Add data to `resume.json`.
3.  Update `_config.yml` with the section name.
4.  Modify `cv.liquid` (`/_layouts/`) with:

    liquid

    `{% when 'new section' %}
  {% include resume/new section.liquid %}`

- `cv.yml` → `/_data/`

  - Here only used if `resume.json` fails, but in general we can use one of them.

---

### 6. Research Page

- Use `research.md` → `/_pages/` to edit the content.
- For repetitive content, create `research.yml` → `/_data/`.

To change the layout/styling:

- Use the `research.md` file directly or create `research.liquid` in `/_includes/`.

---

### 7. Teaching Page

- To add/edit content, use `teaching.yml` → `/_data/`
- To change styling, modify `teaching.md` → `/_pages/`, or create `teaching.liquid`

---

### 8. People Page

- To change names, images, or addresses: edit `profiles.md` → `_pages/`
- To change layout: use `profiles.liquid` → `/_layouts/`
- For personal bios: use `about_joan.md`, `about_einstein.md` → `/_pages/`

  - You can create additional `.md` files for more people, or add to existing ones.

To customize how these sections are displayed, you can also style them directly in the `.md` files.
