# TITLE  
**AI Policy Is No Longer Just Talk**

---

## SHORT DESCRIPTION OF WHAT YOU AIMED TO ACCOMPLISH

The goal of this project was to collect and analyze laws, regulations and policy strategies related to artificial intelligence around the world in order to understand how AI is positioned in the real world. AI‑policy discussions are often dominated by subjective commentary, so I aimed to use text analysis to map the current landscape in a structured, neutral way. This project also served as an opportunity to explore multi‑API data collection, experiment with GPT‑powered keyword extraction, and practise pandas‑based text analysis.

I wanted to know how governments actually regulate AI and to see whether regulation means limiting use or building frameworks to allow safe deployment. The plan was to use API data collection rather than unreliable web‑scraping, apply Python notebooks to clean and merge datasets, and then perform text analysis on policy documents to reveal keywords and themes.

---

## SHORT DESCRIPTION OF YOUR FINDINGS

The analysis showed that the Trump‑era AI Action Plan was not as deregulatory as many assumed; its focus was on building rules to enable AI systems to be commercialised safely rather than on restricting their use. The data also revealed that the term “regulation” has different ethical lenses across countries: it may refer to promoting responsible adoption rather than limiting innovation. In contrast to claims from industry insiders, AI legislation is not being loosened indiscriminately; instead, most countries are codifying how AI should be developed, marketed and used. Each nation has slightly different ethical priorities, which shapes their approach to governing AI.

---

## SUMMARY OF THE DATA COLLECTION PROCESS

This project relied heavily on publicly available data via APIs and official documents. I avoided scraping from unstructured webpages wherever possible and instead looked for authoritative sources. A curated list of policies and acts was prepared manually as a benchmark.

### Data‑collection notebooks and sources

- **`make_AIActlist.ipynb`** – used the Global AI Regulation Tracker API to build a list of AI laws, guidelines and policies worldwide. Data were saved as `ai_regulation_list.csv`.  
  - API: https://www.techieray.com/GlobalAIRegulationTracker

- **`update_US_congress.ipynb`** – queried the Congress.gov API to check the current status of each U.S. bill and produce `updated_ai_regulation_list_US3.csv`.  
  - API: https://api.congress.gov/

- **`marge.ipynb`** – merged multiple lists of AI legislation (from Techieray and Congress) into a unified dataset (`ai_regulation_list2.csv`) and manually checked missing values such as publication dates.

- **`count.ipynb`** – aggregated the number of AI rules per country and category, providing a ready‑to‑visualise dataset for charts.

- **`analays_aipanda.ipynb`** – processed U.S. and Japanese AI strategy PDFs. This notebook:  
  - Extracted full text from PDFs via PyMuPDF;  
  - Split the text into ~4 000‑token chunks using tiktoken;  
  - Queried GPT‑4 for promotion and regulation keywords in each chunk;  
  - Aggregated keyword candidates across all chunks and selected the top 10 appearing in both countries;  
  - Counted keyword frequency and calculated the promotion–regulation score:  
    \[
    \text{score} = \frac{\text{promotion\_count} - \text{regulation\_count}}{\text{promotion\_count} + \text{regulation\_count}}
    \]  
  - Extracted subjects and unique keywords via GPT‑4.

- **`wordcloud.ipynb`** – generated word‑cloud images from the extracted keywords for visualisation.

### Created datasets and files

- **`ai_regulation_list2_merged_SP.csv`** – final dataset of AI laws, guidelines and strategies from the United States, United Kingdom, European Union, China, South Korea, India and Japan. Manual checks were performed to correct missing or incorrect entries.

- **`pivot_result.csv`** – summarised the number of active AI rules per country for Datawrapper charts.

- **`ai_policy_keywords_clean.csv`** – collected keywords extracted via GPT from AI‑policy documents.

- **`keyword_pivot.csv`** – refined keyword list used to calculate promotion vs regulation scores.

- **Policy PDFs** – documents such as *Americas AI Action Plan* (US) and *Japan AI Strategy 2022* were downloaded and analysed as primary sources.

---

## OVERVIEW OF THE DATA ANALYSIS PROCESS

This project followed a two‑stage workflow: data collection (Task A) and text analysis (Task B).

### Task A – Building the dataset

- Compile a ground‑truth list of AI policies and acts to evaluate data quality.
- Use multiple APIs to find comprehensive datasets. The Global AI Regulation Tracker provided the most complete listing.
- Verify U.S. bills by querying the Congress.gov API.
- Merge and refine the datasets, filling gaps (e.g. publication dates) through manual research.
- Summarise counts of active laws and guidelines for each country and category.

### Task B – Analysing policy documents

- Extract full text from PDF policy documents (US and Japan) using PyMuPDF.
- Split text into chunks (~4 000 tokens) with tiktoken to stay within GPT‑4 limits.
- Query GPT‑4 to suggest synonyms and keywords related to “regulation” and “promotion” for each chunk.
- Aggregate and select keywords across all chunks, choosing the top 10 common terms between US and Japanese policies.
- Count occurrences of each keyword in the entire document and calculate a promotion vs regulation score.
- Identify actors and unique terms for each country via further GPT‑4 analysis.
- Visualise results using word clouds and Datawrapper charts.

---

## WHAT NEW SKILLS, APPROACHES, ETC. YOU USED OR WHERE YOU GREW

- **Discovering API alternatives to web scraping:** I initially struggled to scrape data reliably but eventually discovered that many organisations publish datasets through APIs. Searching for the right API saved time and improved data quality.
- **Caution with AI outputs:** GPT‑4’s flexibility can produce inconsistent results and reflect personal bias. This project taught me to treat AI‑generated tags and clusters carefully and to complement them with rule‑based methods. Learning more about regular expressions and machine learning may help build more robust keyword extraction.
- **Appreciation for pandas fundamentals:** Despite using advanced tools, most analyses still depended on organising and cleaning data with pandas. Strong fundamentals were essential for merging datasets, computing scores, and preparing visualisation‑ready tables.

---

## THINGS YOU TRIED OR WANTED TO DO BUT DIDN’T HAVE TIME OR SKILLS

- **Keyword annotation and summarisation within each country’s policy:** A more granular annotation of regulation and promotion keywords per document was planned, but a comprehensive dataset for all countries could not be found.
- **Timeline extraction:** I hoped to identify AI policies taking effect after September 2025 to present a roadmap of future regulations, but time constraints prevented this.
- **Expanding the scope:** I wished to analyse more countries and to verify the accuracy of the datasets more thoroughly, but limited time and resources restricted the breadth of the study.

---

## WEBSITE AND REPOSITORY LINKS

- **Published Website:** [https://yasu25-ny.github.io/project_3/] 
- **Analysis Repository:** [https://github.com/yasu25-NY/projct3_data/] 
