# Network Analysis of Dark Characters

> A social network analysis of the Netflix series **Dark** — mapping the tangled web of relationships across time using graph theory and centrality measures.

---

## 📖 Overview

*Dark* is one of the most cast-intensive TV shows ever made, featuring 150+ main characters and 80+ supporting cast members spread across multiple timelines and generations. This project applies **network analysis** and **mathematical graph theory** to uncover hidden connections, identify key characters, and visualize the complex relationship structure of the show.

Characters are treated as **nodes** in the network, while **edges** represent relationships — weighted by the number of interactions between characters.

---

## Key Features

- **Betweenness & Closeness Centrality** analysis to identify the most influential characters
- **Interactive network graph** built with vis.js — click any character to explore their connections
- **Web-scraped character data** including thumbnails, family trees, and relationship types
- **Color-coded relationship edges** (family, in-law, grandparents, killed-by, lovers, etc.)
- Season-wise character CSV datasets for granular analysis

---

## Tech Stack

| Layer | Tools |
|---|---|
| Data Collection | Python, BeautifulSoup4, Requests, Urllib3 |
| Data Processing | Pandas, tqdm, Regex |
| Data Format | CSV → JSON |
| Visualization | vis.js, HTML, CSS, JavaScript |

---

## Project Structure

```
dark-characters-network/
│
├── src/
│   ├── crawler.py              # Scrapes character data from the Dark wiki
│   └── process_nodes.py        # Cleans data and prepares nodes/edges
│
├── data/
│   └── raw/
│       ├── characters_relationship.csv   # Character relationship data
│       └── characters_thumbnails.csv     # Character image URLs
│
├── data/img/
│   └── characters/             # Downloaded character thumbnails
│
├── index.html                  # Main interactive visualization page
├── network.js                  # vis.js network graph logic
└── css/
    └── styles.css
```

---

## Getting Started

### Prerequisites

```bash
pip install beautifulsoup4 pandas tqdm requests urllib3
```

### 1. Scrape Character Data

```bash
python src/crawler.py
```

This will populate `data/raw/characters_relationship.csv` and `data/raw/characters_thumbnails.csv`.

### 2. Process Nodes & Edges

```bash
python src/process_nodes.py
```

This cleans the data, removes unwanted relationships (adoptive, great-grandparent, etc.), and prepares it for visualization.

### 3. Launch the Visualization

Open `index.html` in your browser. No server required.

---

## Results

The network graph reveals:

- **Hannah Kahnwald** and **Charlotte Doppler** emerge as high-betweenness centrality nodes — acting as bridges between major family clusters
- Seemingly minor characters are revealed to have outsized influence on the narrative
- The Kahnwald, Nielsen, Doppler, and Tiedemann family lines form the four primary clusters in the network

### Betweenness Centrality Heatmap
Characters ranked by their role as connectors across the network — higher values indicate characters who link otherwise-separate groups.
