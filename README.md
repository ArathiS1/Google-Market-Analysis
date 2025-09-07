# Google Market Position Analysis: A Data-Driven Dashboard   

![Power BI](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-0078D4?style=for-the-badge&logo=powerbi&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)

## 🎯 Topic
Comprehensive Market Intelligence: A multi-faceted analysis of Google's market share trends across its core and emerging product lines to assess overall business health and strategic positioning.

## ❓ Problem Statement
In the rapidly evolving tech landscape, Google's dominance is being challenged on multiple fronts. Key business questions needed answers:
1.  Is Google's core revenue engine (Search) maintaining its dominance?
2.  Is its ecosystem gatekeeper (Chrome Browser) gaining or losing traction?
3.  How successful is its foray into consumer hardware (Pixel phones)?
4.  Most critically, is Google effectively competing in the next paradigm shift represented by AI Chatbots, or is it at risk of disruption?

Without a unified view of these metrics, identifying correlated trends and strategic vulnerabilities is difficult.

## 🎯 Objective & Solution
**Objective:** To holistically analyze Google's market position by visualizing and interpreting year-over-year share trends for its key products, determining whether its overall stance is strengthening or weakening.

**Solution:** I developed an **interactive Power BI Dashboard** that synthesizes four distinct market share datasets into a single pane of glass. This solution provides:
*   A **real-time view** of current market shares.
*   A **visual trend analysis** for each product category.
*   A **direct comparison** against main competitors.
*   A **data-driven conclusion** on Google's overall market position.

## 🔧 Tools & Technologies Used
*   **Data Analysis & Visualization:** Microsoft Power BI (Power Query, DAX)
*   **Data Sourcing & Manipulation:** SQL (for hypothetical extraction)
*   **Version Control & Repository:** Git & GitHub
*   **Project Documentation:** Markdown

## 📊 Methodology & Process
The project followed a structured data analysis lifecycle:

1.  **Data Acquisition:**
    *   Simulated the collection of worldwide market share data from industry-leading sources for four categories.

2.  **Data Cleaning & Transformation (ETL) with Power Query:**
    *   Standardized date formats across all datasets.
    *   Handled null and placeholder values (e.g., replacing zeros with `null` in the AI dataset for accurate charting).
    *   Renamed columns for clarity (e.g., `Google Gemini` -> `Gemini`, `Google` (vendor) -> `Pixel`).
    *   Structured data for time-series analysis.

3.  **Data Analysis & Visualization:**
    *   Created individual line charts for each market to visualize trends.
    *   Designed a unified dashboard with synchronized filters for a holistic view.
    *   Used DAX to calculate key metrics and growth rates.

4.  **Interpretation & Reporting:**
    *   Synthesized visual findings into a concise, actionable summary.
    *   Delivered a final verdict on Google's market position.


## 📈 Results & Business Impact


### Key Results & Strategic Insights

| Product Line | Market Position | Trend | Business Impact & Interpretation |
| :--- | :--- | :--- | :--- |
| **Google Search** | Dominant (90% Share) | → **Stable** | **Low Risk.** The primary revenue source is secure. Strategy can focus on monetization efficiency, not defense. |
| **Chrome Browser** | Dominant (65%+ Share) | ↗ **Increasing** | **High Strength.** Growing ecosystem control protects the search business and creates new integration opportunities. |
| **Pixel Hardware** | Niche Player (<3% Share) | ↗ **Volatile but Increasing** | **Positive Signal.** Shows brand strength and potential for ecosystem growth, though it remains a minor revenue contributor. |
| **Gemini AI** | Minor Player (<3.5% Share) | ↘ **Stagnant/Decreasing** | **High Risk.** This is the critical strategic threat. Indicates potential vulnerability to market disruption by OpenAI/Microsoft. Urgent action is required. |

**Overall Conclusion:** Google's present is secure, but its future is challenged. The core business is robust, but the significant underperformance in the AI space signals a critical strategic threat that could erode its dominance long-term.

**Business Impact:** This dashboard provides clear, evidence-based guidance for strategic investment:
*   **Maintain & Monetize:** Continue investing in Search and Browser.
*   **Selective Growth:** Continue the measured growth of the Pixel division.
*   **Allocate Urgently:** Divert significant resources, talent, and focus to the AI division (Gemini) to avoid existential future risk.

**Actionable Recommendations:**
1.  **Immediate:** Launch a strategic review of Gemini's product-market fit, user acquisition, and differentiation versus ChatGPT.
2.  **Short-term:** Leverage Chrome's dominance to more deeply integrate and promote Gemini features to a captive audience.
3.  **Long-term:** Consider more aggressive investment in AI research and development, potentially through acquisitions, to close the innovation gap.


## 💡 SQL Examples (Hypothetical Data Extraction)

```sql
-- Query to get the latest AI Chatbot market shares
SELECT Date, ChatGPT, Gemini, Copilot, Perplexity
FROM ai_chatbot_market_share
WHERE Date = (SELECT MAX(Date) FROM ai_chatbot_market_share)
ORDER BY Date DESC;

-- Query to calculate the 6-month trend for Google Search share
SELECT 
    MIN(CASE WHEN Date = '2024-08-01' THEN Google END) AS Start_Share,
    MAX(CASE WHEN Date = '2025-02-01' THEN Google END) AS End_Share,
    (MAX(CASE WHEN Date = '2025-02-01' THEN Google END) - MIN(CASE WHEN Date = '2024-08-01' THEN Google END)) AS Change
FROM search_engine_market_share;

-- Query to get average browser share for the last quarter
SELECT 
    AVG(Chrome) AS Avg_Chrome_Share,
    AVG(Safari) AS Avg_Safari_Share,
    AVG(Edge) AS Avg_Edge_Share
FROM browser_market_share
WHERE Date BETWEEN '2025-01-01' AND '2025-03-01';
