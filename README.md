
### Student Name: Tống Mỹ Thanh Ngân
### Student ID: 106216298
### Unit: COS30045
### Lecturer: Mr. Nghia Quach
### Story title: Big screen, big bill? – how TV screen size and screen technology affect energy use in Australia.
---------------------------------------------------------------------------------------------------------------------------------------------

# Who is the audience?
- The audience for your visualisation is Australian households who want to buy a new TV.
- Characteristics: 
    + They are everyday shoppers, not technical experts. 
    + They rely on the star ratings of each product when making purchasing decisions and want to keep their electricity bills under control.

# What they want to know
"If I buy a bigger TV, how much more electricity will it use per year and which type should I pick?". Therefore, the most important questions for this audience include: 
1. What sizes of TV are normally on sale?
2. How much more energy does a bigger screen use?
3. Does the panel technology (LCD, LCD (LED), OLED) change the running cost?
4. What should I do when I choose?

# Story in five parts
1. **Setting**: An Australian household is shopping for a new TV. They assume that bigger TVs must cost more and notice that each product has a star rating. However, they do not understand what kWh/year means for their electricity bill or whether screen technology affects their energy consumption.
2. **Conflict**: A high or good star rating does not necessarily mean a lower electricity bill because star ratings only compare TVs of a similar size. Models of the same size can still differ by hundreds of kWh/year. For example, small OLED TVs can use almost twice as much energy as small LCD TVs.
3. **Evidence**: 
    + Large vs small:  average = ≈746 vs ≈128 kWh/year (≈ 5.8×)
    + Small OLED vs small LCD:  = 233.3 vs 122.7 kWh/year (≈ 1.9×)
    + 65-inche models range from about 207 to 1,135 kWh/year.
4. **Chart**: A grouped bar chart (size groups on the x-axis, one bar per screen technology, y = average kWh/year, zero baseline). 
5. **Resolution**: 
    + Size is the biggest driver of running cost
    + Compare kWh/year rather than stars alone
    + Think twice about a small OLED if energy cost matters.

# Storyboard
| # | Step | Visual |
|---|------|--------|
| 1 | **Issue** – a bigger TV may mean a bigger power bill | Headline + key numbers |
| 2 | **Set the scene** – most TVs for sale are range from middle to large size | Histogram of screen sizes; brand pie chart |
| 3 | **Demonstrate** – energy rises with screen size | Scatter plot (inches vs kWh/year) |
| 4 | **Simplify** – small / medium / large averages and the dollar gap | Bar chart + cost table |
| 5 | **Dig deeper** – technology matters most for small TVs (OLED ≈ 2× LCD) | Grouped bar chart + table |
| 6 | **Recommend** – choose size first, compare kWh/year, watch small OLEDs | Numbered advice list |

# Key findings
- About 4,500 models from 75 brands are in the cleaned data (Statistics following GroupBy by Brand_Reg).
- Models cluster at between about 103 and 192 cm, with peaks in the 128–141 cm and 154–166 cm (Histogram chart).
- Average energy use rises with size: 
    + Large ≈ 746 kWh/year.
    + Medium ≈ 382 kWh/year.
    + Small ≈ 128 kWh/year.
- Mean kWh/year by technology (large / medium / small): 
    + LCD 659.6 / 357.5 / 122.7 
    + LCD(LED) 756.8 / 384.1 / 126.9
    + OLED 716.2 / 390.7 / 233.3
- Small OLED TVs use almost twice the energy of small LCD TVs. Furthermore, for medium and large TVs, technology matters much less than size.

-------------------------------------------------------------------------------------------------------------------------
# About the data

# Data source
A data set published by the Australian Government, containing information about the energy consumption of appliances sold in Australia, will be used for Exercise 1-3. The version of the data set is "tv_2026_02_15.csv".

# Data processing
All processing was done in KNIME Platform.

# Privacy
The data describes products (TV models), not people. It contains no personal or sensitive information.

# Accuracy and limitations
- Energy values are **labelled** (test-based) consumption in kWh/year, not measured use in a real home; actual use depends on viewing hours, brightness settings and standby.
- Size category averages in Figure 4 (≈ 746 / 382 / 128 kWh) were read from the KNIME chart and are approximate; the technology averages in Figure 5 are the exact values from the KNIME table.
- The category boundaries leave small gaps (43″– 44″ and 65″– 66″), so a few sizes may fall outside the three groups, depending on rounding.
- Means can be pulled up by extreme models (e.g. one ~114″ model at about 2,650 kWh/year), and the number of models in each group differs, so a model count does not equal units sold.
- The dollar figures on the website assume 30 c/kWh purely for illustration; this is not from the dataset.
- Model counts per brand show how many models exist, not how many TVs were sold or market share.

# Ethics
No personal data is used. Brand names are shown only to describe the market; no claim is made that one brand is better or worse. The advice is general and is based on averages, so individual models can differ – readers are encouraged to check the kWh/year label of the specific TV they are considering. Visuals use zero-based axes and avoid truncation to prevent misleading comparisons.

-------------------------------------------------------------------------------------------------------------------------

# GenAI Declaration

# Tools used
- **Claude (Anthropic)**: chat assistant. I used Claude for:
   + Developing the website: the HTML structure and CSS styling of the Home, Televisions, and About page (including header,body,footer), following my own design colours and layout which I listed out  before proceeding with the work.
   + Drafting the website text (`index.html`), and the README structure.
   + Supporting me complete Javascript code for the Interactive Appliance Energy Calculator in the Home Page.
   + Suggesting the background and story structure for Exercise 3, based on my KNIME results from Exercises 1 and 2.
   + Helping me prepare for the Demonstration 1 checklist.

- **GitHub Copilot in VS Code**: code assistant. I used it for debugging the code, for example finding syntax errors and fixing layout and styling bugs in HTML, CSS and JavaScript.

# Example prompts
- "Using the files I attached, restyle the section I sent so that it follows the general design defaults I have already used across my website."
- "I changed some parts of televisions.html. Please restyle the new content so it stays consistent with the rest of the page."
- "I added a CSV Writer node and chose a file location, but the dialog shows the 'Local file system' tab. What should I choose so the output file is saved in the workflow's data folder and included when I export the .knwf?"
- "Help me complete the COS30045 Demonstration 1 checklist using my data file, and check my row counts, brand counts and data types."

# What I checked myself
- I created all KNIME workflows, data processing and charts myself in both Exercises 1 and 2, and ran them from start to finish without errors about the data set.
- I compared every number on the website with my KNIME outputs. Where a value was read from a chart instead of a table, I asked where it came from and replaced it or marked it as approximate.
- I confirmed the row counts: 4,724 raw rows, 4,710 after the Available filter and 4,508 after the SoldIn filter.
- I opened the website in a browser, checked that images load, that the Home, Televisions and About us pages work and that my name is in every footer.
- I read through the AI-generated text and code, edited it where it was unclear or uncorrect.  I can explain each chart, node by my own way of understanding. 



