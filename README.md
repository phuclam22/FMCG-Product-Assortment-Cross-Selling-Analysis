# FMCG Product Assortment & Cross-Selling Analysis

## Project Overview
This repository contains an end-to-end **Market Basket Analysis** project built entirely within Power BI. Designed with a Commercial/Retail Analytics mindset, this project transforms raw transactional data into actionable business strategies for product assortment, store layout optimization (planogram), and cross-merchandising.

Instead of relying on Python/Machine Learning libraries, this project showcases **Advanced DAX** capabilities to mathematically calculate association rules (Support, Confidence, and Lift) and visualize complex product networks.

## Business Value & Objectives
In the fast-moving consumer goods (FMCG) and grocery retail sector, understanding how products interact in a customer's basket is critical. This project answers key commercial questions:
* **Product Assortment:** Which products act as "Hubs" (traffic drivers) and which act as "Satellites" (add-on purchases)?
* **Space & Shelf Productivity:** How should products be placed next to each other on the physical store layout to maximize organic cross-selling?
* **Promotional Strategy:** Which product combinations are highly associated but underperforming in volume, indicating a prime opportunity for bundle promotions?

## Dataset
* **Source:** Retail Groceries Dataset (`Groceries.csv`)
* **Scale:** ~7,800+ unique transactions, encompassing 170 distinct product categories.
* **Structure:** Unstructured, varied-length transactional data transformed into a normalized tabular format.

## Tech Stack & Techniques
* **Tool:** Power BI Desktop
* **Data Preparation (Power Query):** Indexing, Unpivoting columns, and data cleansing to normalize multi-item receipts into a 1-to-many relationship structure.
* **Data Modeling (DAX):** Generating Cartesian products using `CROSSJOIN` and `VALUES` to create a matrix of all possible product combinations (14,365 unique pairs).
* **Advanced DAX (Calculations):** Extensive use of Variables (`VAR`), Context Transition, `FILTER`, `SELECTCOLUMNS`, and `INTERSECT` to calculate basket metrics.
* **Custom Visuals:** Integration of *ZoomCharts Network* for graph-based visualization.

## The 3 Core Metrics (Association Rules)
The analytical engine of this dashboard is built on three foundational metrics:
1. **Support:** The frequency of a product pair appearing in total transactions. *(Measures business scale/revenue potential).*
2. **Confidence:** The directional probability that a customer buys Product B given they have already placed Product A in their basket. *(Measures cross-selling direction).*
3. **Lift:** The strength of the association. A Lift > 1 indicates that the products are bought together more often than by random chance. *(Measures true product affinity).*

## Dashboard Highlights & Insights
The interactive dashboard features three main components:

1. **Product Affinity Hubs (Network Chart):**
   * Visually maps product clusters. Revealed massive traffic hubs like **Yogurt**, **Whipped/Sour Cream**, and **Root Vegetables**.
   * *Actionable Insight:* These hub products should be strategically placed to guide store traffic, while satellite items (e.g., Berries, Herbs) should be cross-merchandised adjacent to them.

2. **Cross-Selling Potential Matrix (Scatter Plot):**
   * Segments product pairs based on *Purchase Frequency (Support)* vs. *Association Strength (Lift)*.
   * *Actionable Insight:* Identified "Niche Combos" (High Lift, Low Support) like `Root Vegetables & Herbs`. These are prime candidates for Trade Marketing campaigns and combo pricing (e.g., "Buy Beef, get 20% off Herbs") to boost volume.

3. **Detailed Basket Association Metrics (Matrix Table):**
   * Provides granular, row-level data for Category Managers to validate decisions and set up Loss Leader strategies based on asymmetrical Confidence scores.

## How to Use This Repository
1. Clone the repository to your local machine.
2. Ensure you have **Power BI Desktop** installed.
3. Open the `Groceries Basket Analysis.pbix` file.
4. Interact with the dashboard by clicking on the nodes in the Network Chart to cross-filter the Matrix and Scatter Plot.
