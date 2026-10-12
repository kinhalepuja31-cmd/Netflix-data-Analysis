**# Netflix-data-Analysis


**Project Overview**

This project delivers a comprehensive Exploratory Data Analysis (EDA) on a raw streaming platform catalog dataset. Moving from a raw database dump to a data-driven business narrative, this analysis provides the quantitative insights required by a modern Content Strategy and Corporate Growth team to optimize streaming library metrics.

**Objectives**

**Data Validation:** Clean raw structural data, handle null fields, convert data types, and remove non-statistical administrative items.

**Trend Identification:** Analyze content mix, catalog seasonality patterns, target audience profiles, original production years, and global footprint distributions.

**Strategic Synthesis:** Translate statistical insights into high-impact corporate recommendations for budget deployment.

Data Cleaning & Pipeline Operations

To ensure complete statistical accuracy across the analytical pipeline, the raw data underwent structured parsing operations using Pandas:

1. Imputation: Null fields within heavy text layers (`director`, `cast`, `country`) were updated with an `'Unknown'` placeholder string to prevent aggregation drop-outs.
2. Maturity Fill: Minor missing values in `rating` were assigned an `'Unknown'` marker. Missing rows in `date_added` and `duration` were dropped due to low volume (<0.1% of the dataset).
3. Data Type Correction: The `date_added` string field was formatted into an analytical `datetime64[ns]` timestamp to unlock timeline feature extractions (`year_added`, `month_added`).
4. Column Dropping: The administrative rows `show_id`, `title`, and `description` were discarded via `df.drop()` as they contain distinct identifiers that yield zero statistical value for macro trends.
5. Array Exploding: Multivalue fields wrapped inside commas (`listed_in` and `country`) were systematically split and exploded into unique index lines to allow individual genre and regional tracking.

Analytical Visualizations Included
The pipeline generates 7 distinct graphical assets to segment the catalog:

**Chart 1: Content Mix Breakdowns** – A proportional evaluation detailing the percentage margin between Movie and TV Show listings.

**Chart 2: Library Additions Velocity** – A chronological timeline mapping the overall growth curve of library uploads.

**Chart 3: Genre Performance Metrics** – A structured distribution tracking individual genres to identify consumer demand trends.

**Chart 4: Target Demographics Matrix** – A breakdown of maturity ratings (TV-MA, TV-14, PG-13) mapping core user age segments.

**Chart 5: Film Asset Duration** – A runtime distribution histogram charting the typical length of movie assets.

**Chart 6: Geographic Output Centers** – A volume matrix mapping international production hubs outside the domestic United States.

**Chart 7: Catalog Upload Seasonality** – A monthly heatmap cross-tabulating release drops to detect calendar-based launch strategies.


Content Strategy Memo: 3 Actionable Business Insights

1. Shift Investment to Episodic Content (The Television Pivot)
**The Trend:** While feature-length movies comprise the clear majority of total historical library volume, TV Show additions feature a significantly faster acceleration curve over modern operating years. 
**Business Impact:** Standalone cinematic assets cause immediate post-viewing drop-offs. Multi-season TV series create predictable, long-term subscriber engagement patterns that lower monthly churn metrics.
**Actionable Insight:** Reallocate 15% of the upcoming slate budget from licensing middle-tier independent feature films into developing multi-season episodic series to maximize weekly active user (WAU) retention.

3. Fund International Co-Productions (The Hyper-Localization Wave)
**The Trend:** Outside of primary operations in the United States, India, South Korea, and the United Kingdom have emerged as the top three content-producing engines in our library.
**Business Impact:** Content engineered in these territories is highly cost-effective to produce compared to domestic budgets, yet features massive cross-border crossover appeal when localized via built-in dubbing and subtitle tracks.
**Actionable Insight:** **Establish formal co-production partnerships with localized studios in Seoul and Mumbai.
Prioritize funding native thrillers and romance dramas that can be cross-distributed globally at a lower cost-per-subscriber acquisition metric.

5. Expand the Low-Cost Unscripted Slate (The Genre Efficiency Pattern)
**The Trend:** Granular analysis of the unnested genre tracking reveals that Documentaries, True Crime, and Reality Formats command a dominant percentage share of the platform's active catalog.
**Business Impact:** Unscripted content achieves highly consistent viewership metrics relative to its production cost, completely avoiding the massive financial liabilities and lengthy turnarounds of prestige scripted dramas.
**Actionable Insight:** Fast-track the development of unscripted docuseries and reality competitions for the next fiscal year. This establishes a high-margin catalog cushion to fill seasonal gaps between flagship scripted releases.




**
