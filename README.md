# ADV SaSS

### User Story 1

- The frontend build chain features a SASS compiler

install sass

```bash
npm install --save-dev sass
```

the command watches the scss written in src and compiles it to **dist** (live)

```bash
npm run sass
```

→ has to be declared in package.json (so it can be run with npm run)

**package.json**

```json
"scripts": {
	"sass": "sass src/scss/main.scss dist/css/style.css --watch"
}
```

- The SASS compiler is used for generating the CSS for the responsive framework of your choice, respecting custom color variables

import the bootstrap scss and use the command above to generate the css of the bootstrap.

**main.scss**

```scss
@import "custom/variables" @import "../../node_module/bootstrap/scss/bootstrap";
```

### User Story 2

- A responsive framework of the developers choice is ready for the frontend development stack

```bash
npm install bootstrap
```

- The responsive framework can be updated without overwriting changes made to the styles

importing the variables **before** importing bootstrap overrides the default bootstrap variables.

Note: they have to be named like the bootstrap variables

**main.scss**

```scss
@import "custom/variables";
@import "../../node_modules/bootstrap/scss/bootstrap";
```

**custom/\_\_variables.scss**

```scss
$primary: #ff6600;
$secondary: #222222;

$font-family-base: "Poppins", sans-serif;

$border-radius: 1rem;

$navbar-dark-bg: #ff6600;

$btn-border-radius: 2rem;
```

### User Story 3

#### Navbar

| Line   | Class / Attribute                              | Device          | Purpose                                                              |
| ------ | ---------------------------------------------- | --------------- | -------------------------------------------------------------------- |
| L7     | `navbar-expand-lg`                             | All             | Collapses to hamburger on mobile/tablet (<992px), expands on desktop |
| L12–15 | `navbar-toggler` + `data-bs-toggle="collapse"` | Mobile / Tablet | Hamburger button, hidden on lg+                                      |
| L16    | `collapse navbar-collapse`                     | All             | Hides nav links on small screens, shows inline on lg+                |
| L18    | `mb-2 mb-lg-0`                                 | Mobile / Tablet | Removes bottom margin on lg+                                         |
| L31    | `ms-lg-3`                                      | Desktop         | Adds left margin to CTA button only on lg+                           |

---

#### Hero Section

| Line   | Class                        | Device | Purpose                                                  |
| ------ | ---------------------------- | ------ | -------------------------------------------------------- |
| L38    | `row align-items-center g-5` | All    | Stacks columns vertically on mobile, side-by-side on lg+ |
| L39    | `col-lg-6`                   | All    | Full-width on mobile/tablet → 50% on desktop             |
| L42–43 | `d-flex flex-wrap gap-3`     | Mobile | CTA buttons wrap to second line on narrow screens        |
| L55    | `img-fluid`                  | All    | Hero image scales to 100% of its container               |

---

#### Stats Bar

| Line | Class            | Device | Purpose                                |
| ---- | ---------------- | ------ | -------------------------------------- |
| L63  | `row g-4`        | All    | Row with gutters for stat columns      |
| L65  | `col-6 col-md-3` | All    | 2 columns on mobile → 4 columns on md+ |

---

#### Features Section

| Line | Class               | Device | Purpose                                                 |
| ---- | ------------------- | ------ | ------------------------------------------------------- |
| L97  | `col-sm-6 col-lg-4` | All    | 1 col mobile → 2 col tablet (sm+) → 3 col desktop (lg+) |

---

#### Pricing Section

| Line | Class      | Device | Purpose                                  |
| ---- | ---------- | ------ | ---------------------------------------- |
| L131 | `col-md-4` | All    | Cards stack on mobile → 3 columns on md+ |

---

#### Testimonials

| Line | Class      | Device | Purpose                                  |
| ---- | ---------- | ------ | ---------------------------------------- |
| L194 | `col-md-4` | All    | Cards stack on mobile → 3 columns on md+ |

---

#### Blog Preview

| Line | Class                                               | Device | Purpose                                  |
| ---- | --------------------------------------------------- | ------ | ---------------------------------------- |
| L225 | `d-flex justify-content-between align-items-center` | All    | Flexbox header row — works on all widths |
| L229 | `col-md-4`                                          | All    | Cards stack on mobile → 3 columns on md+ |

---

#### Footer

| Line | Class                     | Device          | Purpose                                                     |
| ---- | ------------------------- | --------------- | ----------------------------------------------------------- |
| L284 | `col-lg-4`                | All             | Brand column: full-width on mobile/tablet → 4/12 on desktop |
| L295 | `col-6 col-lg-2`          | All             | Link columns: 2 per row on mobile → 5 columns on desktop    |
| L359 | `flex-column flex-md-row` | All             | Bottom bar stacks on mobile → row layout on md+             |
| L362 | `mt-3 mt-md-0`            | Mobile / Tablet | Top margin for social icons when stacked; removed on md+    |

---

#### Bootstrap Breakpoints Reference

| Prefix   | Breakpoint | Typical device              |
| -------- | ---------- | --------------------------- |
| _(none)_ | 0px+       | Mobile (default)            |
| `sm`     | ≥576px     | Large mobile                |
| `md`     | ≥768px     | Tablet                      |
| `lg`     | ≥992px     | Desktop                     |
| `xl`     | ≥1200px    | Wide desktop (16:9 / 16:10) |
