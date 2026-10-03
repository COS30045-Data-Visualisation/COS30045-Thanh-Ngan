# COS30045- Thanh Ngan
# Exercise 3 – Communicating Data Insights (COS30045)

**Student:** Tống Mỹ Thanh Ngân · **ID:** 106216298 · **Lecturer:** Mr. Nghia Quach

**Website:** open `index.html` (or the GitHub Pages URL for this repository).
**Story title:** *Big screen, big bill? – how TV screen size and screen technology affect energy use in Australia.*

---

## Data Story

### Audience
Australian households who are about to buy a new TV. They are everyday shoppers, not technical experts. They see a star-rating label in the shop and want to keep their electricity bill under control.

### What they want to know
*"If I buy a bigger or fancier TV, how much more electricity will it use per year – and which type should I pick?"* The most important questions for this audience are therefore:
1. What sizes of TV are normally on sale?
2. How much more energy does a bigger screen use?
3. Does the screen technology (LCD, LCD (LED), OLED) change the running cost?
4. What should I do when I choose?

### Guidelines used for the visualisation story
- Plain language, no jargon; explain stars vs kWh/year.
- One idea per chart, with a short takeaway sentence under or beside each.
- Same colour meaning throughout; start bar charts at zero so differences are not exaggerated.
- Move from the broad picture (market) → one driver (size) → a second driver (technology) → advice.

### Story in five parts (also shown on the website)
1. **Setting – reader and prior knowledge:** an Australian household buying a TV. They know bigger TVs cost more and that labels have stars; they don't know what kWh/year means for their bill or whether screen technology changes it.
2. **Conflict – the problem/surprise:** a good star rating does not mean a low bill (stars only compare TVs of similar size); models of the same size still differ by hundreds of kWh/year; and small OLED TVs use almost double the energy of small LCD TVs.
3. **Evidence – the numbers:** large vs small average = ≈ 745 vs ≈ 158 kWh/year (≈ 4.7×); small OLED vs small LCD = 233.3 vs 122.7 kWh/year (≈ 1.9×); 65" models range from about 200 to 1,100 kWh/year.
4. **Chart – best visual:** a grouped bar chart (size groups on the x-axis, one bar per screen technology, y = average kWh/year, zero baseline). A hand-drawn sketch of it is on the website, followed by the finished chart (Figure 5).
5. **Resolution – what the reader should do/believe:** size is the biggest driver of running cost; compare kWh/year rather than stars alone; think twice about a small OLED if energy cost matters.

### Storyboard
| # | Step | Visual |
|---|------|--------|
| 1 | **Issue** – a bigger/fancier TV may mean a bigger power bill | Headline + key numbers |
| 2 | **Set the scene** – most TVs for sale are mid-to-large | Histogram of screen sizes; brand pie chart |
| 3 | **Demonstrate** – energy rises with screen size | Scatter plot (inches vs kWh/year) |
| 4 | **Simplify** – small / medium / large averages and the dollar gap | Bar chart + cost table |
| 5 | **Dig deeper** – technology matters most for small TVs (OLED ≈ 2× LCD) | Grouped bar chart + table |
| 6 | **Recommend** – choose size first, compare kWh/year, watch small OLEDs | Numbered advice list |

### Key findings
- About 4,500 models from 75 brands are in the cleaned data; models cluster at roughly 110–190 cm, with peaks near 135 cm and 160 cm.
- Average energy use rises with size: large ≈ 745, medium ≈ 403, small ≈ 158 kWh/year.
- Mean kWh/year by technology (large / medium / small): LCD 659.6 / 357.5 / 122.7; LCD (LED) 756.8 / 384.1 / 126.9; OLED 716.2 / 390.7 / 233.3.
- Small OLED TVs use almost twice the energy of small LCD TVs; for medium and large TVs, technology matters much less than size.

---

## About the data

### Data source
Australian TV energy-rating dataset supplied for COS30045 Exercises 1–3 (one row per TV model: brand, regions sold in, availability status, screen size in cm, screen technology, star rating and labelled energy consumption in kWh/year). *(Add the exact name, publisher, URL, licence and date of the file you downloaded from Canvas / data.gov.au here.)*

### Data processing
All processing was done in KNIME:
- **Column Filter** – kept only the columns needed for each question.
- **String Cleaner / String Replacer** – fixed inconsistent capitalisation and merged brand-name variants ("samsung electronics" → "samsung", "q.bell" → "qbell").
- **Nominal Value Row Filter** – removed unavailable models and models not sold in Australia.
- **GroupBy / Sorter** – counted models per brand (75 brands; largest = Samsung with 1,096 models).
- **Expression + Number Rounder** – converted screen size from cm to inches (× 0.393701) and rounded to whole inches.
- **Expression** – created size categories: small (< 43″), medium (44″–65″), large (> 66″).
- **Pivot + GroupBy** – mean energy consumption by screen technology within each size category.
- **Histogram, Scatter Plot, Bar Chart, Pie Chart** – charts; screenshots were cropped to remove KNIME interface elements. The grouped bar chart on the website is redrawn with Chart.js using the exact table values from KNIME.

### Privacy
The data describes products (TV models), not people. It contains no personal or sensitive information.

### Accuracy and limitations
- Energy values are **labelled** (test-based) consumption in kWh/year, not measured use in a real home; actual use depends on viewing hours, brightness settings and standby.
- Size category averages in Figure 4 (≈ 745 / 403 / 158 kWh) were read from the KNIME chart and are approximate; the technology averages in Figure 5 are the exact values from the KNIME table.
- The category boundaries leave small gaps (43″–44″ and 65″–66″), so a few sizes may fall outside the three groups, depending on rounding.
- Means can be pulled up by extreme models (e.g. one ~114″ model at about 2,650 kWh/year), and the number of models in each group differs, so a model count does not equal units sold.
- The dollar figures on the website assume 30 c/kWh purely for illustration; this is not from the dataset.
- Model counts per brand show how many models exist, not how many TVs were sold or market share.

### Ethics
No personal data is used. Brand names are shown only to describe the market; no claim is made that one brand is better or worse. The advice is general and is based on averages, so individual models can differ – readers are encouraged to check the kWh/year label of the specific TV they are considering. Visuals use zero-based axes and avoid truncation to prevent misleading comparisons.

---

## AI Declaration

> **Please review and edit this section so it matches exactly how you used AI.**

I used the AI assistant **Claude (Anthropic)** to help with this exercise. Specifically:
- To suggest an audience, storyboard and story structure based on my KNIME results from Exercises 1 and 2.
- To draft the website text (`index.html`), CSS styling and the README structure.
- To help write the Chart.js code for the grouped bar chart.

The KNIME workflows, data processing and charts were produced by me in Exercises 1 and 2. I checked the numbers in the story against my KNIME outputs, and I take responsibility for the final content. Chart.js (MIT licence) is included locally in `js/chart.umd.js`.
