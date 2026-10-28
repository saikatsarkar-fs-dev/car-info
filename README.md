# Car/Info

A multi-page field guide to six popular Indian cars, built with hand-written HTML and CSS for a college assignment. No JavaScript, no framework, no build step.

**Live site:** <https://saikatsarkar-fs-dev.github.io/car-info/>

## What is this?

Car/Info documents the Maruti Suzuki Swift, Hyundai Creta, Tata Nexon, Honda City, Mahindra Thar and Toyota Fortuner. Each car has a detail page with specifications, dimensions, ownership notes and sources. A separate page compares all six side by side.

The design takes its cues from Indian highway signage and printed road atlases: warm paper, ink, saffron and deep green, with Fraunces and Archivo, route badges, dashed rules and sharp photo frames. Light and dark themes follow the operating system automatically.

## Pages

| Page | What it covers |
| --- | --- |
| `index.html` | Introduction, three featured cars and the editorial route |
| `cars.html` | All six cars, with a CSS-only body-style filter |
| `compare.html` | A 17-row specification table and quick picks |
| `about.html` | Project notes, method, accessibility statement and full image credits |
| `contact.html` | GitHub and email links, plus correction guidelines |
| `404.html` | A “wrong turn” page with links back into the site |
| `cars/maruti-suzuki-swift.html` | Swift specifications and ownership notes |
| `cars/hyundai-creta.html` | Creta specifications and ownership notes |
| `cars/tata-nexon.html` | Nexon specifications and ownership notes |
| `cars/honda-city.html` | City specifications and ownership notes |
| `cars/mahindra-thar.html` | Thar specifications and ownership notes |
| `cars/toyota-fortuner.html` | Fortuner specifications and ownership notes |

## Features

- **No JavaScript.** Every page works with scripting disabled. The garage filter uses radio inputs and `:has()`; browsers without `:has()` show all six cars and hide the filter.
- **Modern CSS.** Cascade layers, custom properties, `oklch()` colours with hex fallbacks, `light-dark()`, `color-mix()`, fluid `clamp()` type and spacing, container queries, and optional cross-document view transitions.
- **Responsive.** Layouts adapt from 320 px phones to wide desktops. The comparison and credits tables scroll horizontally and are keyboard focusable.
- **Accessible.** Skip link, visible `:focus-visible` styles, semantic landmarks, one `h1` per page, descriptive alt text, labelled table regions and reduced-motion support.
- **Automatic themes.** `color-scheme: light dark` and `light-dark()` follow the operating system; there is no theme toggle.
- **Print styles.** Navigation, filters and decorative elements are removed when printing, and the comparison table is simplified.
- **Relative URLs.** The site works from a project subpath such as `/car-info/` as well as from a local folder.

## Project structure

```text
car-info/
├── index.html
├── cars.html
├── compare.html
├── about.html
├── contact.html
├── 404.html
├── cars/
│   ├── maruti-suzuki-swift.html
│   ├── hyundai-creta.html
│   ├── tata-nexon.html
│   ├── honda-city.html
│   ├── mahindra-thar.html
│   └── toyota-fortuner.html
├── assets/
│   ├── css/main.css
│   └── favicon.svg
├── .github/workflows/pages.yml
├── LICENSE
└── README.md
```

All styling lives in `assets/css/main.css`. There are no generated files and no dependencies to install.

## Local preview

Open `index.html` directly in a browser, or serve the folder so root-relative behaviour matches GitHub Pages:

```sh
# Python 3
python -m http.server 8000
```

Then visit <http://localhost:8000/>.

With Node.js installed, any static server works too:

```sh
npx serve .
```

If you use VS Code, the Live Server extension can serve the folder without any project configuration.

## Deployment

The site deploys to GitHub Pages with the workflow in `.github/workflows/pages.yml`. On every push to `main`, it uploads the repository root as a Pages artifact and deploys it. The workflow can also be triggered manually from the Actions tab.

To enable it on a fresh fork or clone:

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
4. Push to `main`, or run **Deploy to GitHub Pages** from the Actions tab.

The expected URL is `https://<username>.github.io/car-info/`. All internal links are relative, so no base-path configuration is needed.

## Data and sources

Specifications and prices were checked in **October 2026** against manufacturer pages, then cross-checked against CarWale and CarDekho where a manufacturer publishes only a starting price or blocks automated access.

- Maruti Suzuki Swift: <https://www.marutisuzuki.com/arena/swift>
- Hyundai Creta: <https://www.hyundai.com/in/en/find-a-car/creta/highlights>
- Tata Nexon: <https://cars.tatamotors.com/nexon/ice.html>
- Honda City: <https://www.hondacarindia.com/honda-city>
- Mahindra Thar: <https://auto.mahindra.com/suv/thar/specs-and-features.html>
- Toyota Fortuner: <https://www.toyotabharat.com/showroom/fortuner/index-fortuner.html>

Prices are ex-showroom and vary by city, variant and model year. Specifications vary by variant; the detail pages list their exact sources. This is a student project, not buying advice, and it is not affiliated with any manufacturer.

## Image credits

All car photographs are hotlinked from Wikimedia Commons at reduced width. No copies are stored in this repository. Each is credited in its page caption and in the table on `about.html`.

| Car | Photograph | Author | Licence | Note |
| --- | --- | --- | --- | --- |
| Maruti Suzuki Swift | [Suzuki Swift (2024) hybrid IMG 8936.jpg](https://commons.wikimedia.org/wiki/File:Suzuki_Swift_(2024)_hybrid_IMG_8936.jpg) | Alexander-93 | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | European-spec hybrid; representative of the Indian generation |
| Hyundai Creta | [2024 Hyundai Creta 1.5 MPi SX(O) (India) front view.png](https://commons.wikimedia.org/wiki/File:2024_Hyundai_Creta_1.5_MPi_SX(O)_(India)_front_view.png) | CARS WORLD Kannada | [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/) | Indian-spec |
| Tata Nexon | [2023 Tata Nexon XZA+ front view.jpg](https://commons.wikimedia.org/wiki/File:2023_Tata_Nexon_XZA%2B_front_view.jpg) | Dairokkan9 | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Indian-spec |
| Honda City | [2026 Honda City e-HEV RS (1).jpg](https://commons.wikimedia.org/wiki/File:2026_Honda_City_e-HEV_RS_(1).jpg) | Chanokchon | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Thai-spec e:HEV RS; Indian trims differ |
| Mahindra Thar | [Mahindra Thar SUV in “Red Rage” colour… 02.jpg](https://commons.wikimedia.org/wiki/File:Mahindra_Thar_SUV_in_%22Red_Rage%22_color_at_Ashiana_Brahmanda,_East_Singbhum_India_(Ank_Kumar,_Infosys_limited)_02.jpg) | Ank Kumar | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Indian-spec, Jharkhand |
| Toyota Fortuner | [2022 Toyota Fortuner 2.8 Legender 4WD 60th Anniversary.jpg](https://commons.wikimedia.org/wiki/File:2022_Toyota_Fortuner_2.8_Legender_4WD_60th_Anniversary.jpg) | Chanokchon | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Thai-spec Legender 4WD; Indian trims differ |

The photographs remain under their respective Creative Commons licences. If you reuse one, follow the licence on its source page. The MIT licence below covers the code, not the photographs.

## Adding another car

1. Copy an existing page in `cars/` and update the title, description, JSON-LD, specifications, sources and image credit.
2. Add a card to `cars.html` with a unique `data-body` value. If you introduce a new body style, add a filter input and a matching filter rule in `main.css`.
3. Add the car to every relevant row in `compare.html`.
4. Add the photo credit to `about.html` and to this README.
5. Update the pager links on the neighbouring detail pages and the “Cars” count on the home page.

## Accessibility notes

- The CSS filter changes what is visible but does not announce a result count. All cars remain in the document and are reachable when no filter is active.
- The filter is hidden in browsers that do not support `:has()`; all six cars are then shown.
- External images and Google Fonts require an internet connection. The text remains readable without either.
- Motion is disabled when `prefers-reduced-motion: reduce` is set.

Corrections are welcome through [GitHub Issues](https://github.com/saikatsarkar-fs-dev/car-info/issues) or by email at <me.saikatsarkar.dev@gmail.com>. Please include the car, the variant and a source.

## Assignment context

This site was built for a college assignment to demonstrate semantic HTML, modern CSS, responsive design, accessibility and responsible use of external media. The constraint was deliberate: no JavaScript, no frameworks and no build step. The CSS-only filter, automatic themes and print styles are part of that exercise.

Manufacturer names, model names and logos are trademarks of their respective owners. Car/Info is an independent student project.

## Licence

The code is released under the [MIT Licence](LICENSE). © 2026 Saikat Sarkar. The written content and design are © 2026 Saikat Sarkar unless otherwise noted. Photographs are credited above and remain under their Creative Commons licences.
