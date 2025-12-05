# Financial-Project
<h1 align="center">📊 Financial Reporting Automation Framework</h1>
<p align="center">
Automated ETL pipeline & analytics dashboard built using <b>Google BigQuery, SQL, Python, and Streamlit</b>.
</p>

<hr>

<h2>📌 Table of Contents</h2>
<ul>
  <li><a href="#overview">Overview</a></li>
  <li><a href="#architecture-diagram">Architecture Diagram</a></li>
  <li><a href="#medallion-architecture">Medallion Architecture</a></li>
  <li><a href="#bronze-layer">Bronze Layer: Raw Data Ingestion</a></li>
  <li><a href="#silver-layer">Silver Layer: Cleaning & Validation</a></li>
  <li><a href="#gold-layer">Gold Layer: Analytical Data Models</a></li>
  <li><a href="#streamlit-dashboard">Streamlit Dashboard</a></li>
  <li><a href="#technology-stack">Technology Stack</a></li>
  <li><a href="#project-structure">Project Structure</a></li>
  <li><a href="#setup--execution">Setup & Execution</a></li>
  <li><a href="#data-quality--error-handling">Data Quality & Error Handling</a></li>
  <li><a href="#contribute">How to Contribute</a></li>
</ul>

<hr>

<h2 id="overview">📘 Overview</h2>
<p>
The <b>Financial Reporting Automation Framework</b> automates the entire lifecycle of financial data processing:
raw ingestion → cleaning → transformation → dimensional modeling → KPI generation → dashboard reporting.
</p>

<p>
This project enables finance teams to analyze key business metrics such as:
<b>Total Revenue, Market Cap, Gross Margin %, Net Profit Margin %, ROI, ROE, ROA</b>,
and also supports predictive forecasting like revenue prediction.
</p>

<h3>✨ Key Features</h3>
<ul>
  <li>Automated ingestion using Bronze → Silver → Gold architecture</li>
  <li>Cleaned & validated datasets with type-formatting and enrichment</li>
  <li>Fully developed Fact & Dimension tables for analytics</li>
  <li>Interactive Streamlit dashboard for visualization</li>
  <li>Revenue forecasting (BigQuery ML or Python Estimator)</li>
  <li>End-to-end SDLC-driven implementation</li>
</ul>

<hr>

<h2 id="architecture-diagram">🏗️ Architecture Diagram</h2>

<pre style="font-size: 15px; font-weight: bold; background: #f4f4f4; padding: 20px; border-radius: 10px; line-height: 1.4;">
+----------------------------+       +-----------------------+       +---------------------------+        +----------------------------+
|      Source (CSV Files)    | ----> |      Bronze Layer     | ----> |       Silver Layer        | ---->  |        Gold Layer          |
|  Raw Financial Dataset     |       |     Raw Tables        |       |  Cleaned & Validated Data |        |  Fact & Dimension Tables   |
+----------------------------+       +-----------------------+       +---------------------------+        +----------------------------+

                                           |
                                           v

                               +----------------------------+
                               |     Streamlit Dashboard    |
                               |  KPIs, Trends, Forecasting |
                               +----------------------------+
</pre>


<hr>

<h2 id="medallion-architecture">🏅 Medallion Architecture</h2>

<h3>1️⃣ Bronze Layer — Raw Data</h3>
<p>Stores the raw CSV as-it is. No transformations applied.</p>

<h3>2️⃣ Silver Layer — Cleaned Data</h3>
<p>
Applies:
<ul>
  <li>Data type casting</li>
  <li>Trimming, formatting</li>
  <li>Null handling</li>
  <li>Standardized column naming</li>
</ul>
</p>

<h3>3️⃣ Gold Layer — Analytics & KPIs</h3>
<p>
Contains:
<ul>
  <li><b>Fact Table: fact_financial_performance</b></li>
  <li><b>Dimensions:</b> dim_company, dim_category, dim_time</li>
  <li>KPI views: vw_kpi_summary, vw_revenue_profitability, returns, efficiency</li>
</ul>
</p>

<hr>

<h2 id="bronze-layer">🥉 Bronze Layer</h2>
<p><b>Dataset:</b> even-blueprint-441418-p2.Bronze_Layer</p>
<p><b>Table:</b> Raw_Financial_Data</p>

<p>Contains raw, unmodified data exactly as uploaded.</p>

<hr>

<h2 id="silver-layer">🥈 Silver Layer</h2>
<p><b>Dataset:</b> even-blueprint-441418-p2.Silver_Layer</p>
<p><b>Table:</b> clean_financial_data</p>

<h3>Transformations Applied:</h3>
<ul>
  <li>SAFE_CAST for numeric conversions</li>
  <li>Trim Company & Category fields</li>
  <li>Market Cap, Revenue, EBITDA sanitization</li>
  <li>Convert Year to INT</li>
  <li>Standard financial naming consistency</li>
</ul>

<hr>

<h2 id="gold-layer">🥇 Gold Layer</h2>

<h3>Dimensional Tables:</h3>
<ul>
  <li>dim_company</li>
  <li>dim_category</li>
  <li>dim_time</li>
</ul>

<h3>Fact Table:</h3>
<p><b>fact_financial_performance</b></p>

<h3>Analytical Views:</h3>
<ul>
  <li>vw_kpi_summary</li>
  <li>vw_revenue_profitability</li>
  <li>vw_return_ratios</li>
  <li>vw_efficiency</li>
  <li>vw_revenue_forecast</li>
  <li>vw_inflation_impact</li>
</ul>

<hr>

<h2 id="streamlit-dashboard">📊 Streamlit Dashboard</h2>

<h3>Visualized Metrics:</h3>
<ul>
  <li>Total Companies</li>
  <li>Total Market Cap (B USD)</li>
  <li>Total Revenue</li>
  <li>Average Net Income</li>
  <li>Revenue vs Net Income Trend</li>
  <li>Revenue Growth %</li>
  <li>Gross Margin %</li>
  <li>Net Profit Margin %</li>
  <li>ROE, ROA, ROI</li>
  <li>Employee Productivity</li>
  <li>Revenue Forecasting</li>
  <li>Inflation Impact</li>
</ul>

<hr>

<h2 id="technology-stack">🛠 Technology Stack</h2>
<ul>
  <li><b>Google BigQuery</b> (Data Warehouse)</li>
  <li><b>SQL</b> (ETL Transformation Logic)</li>
  <li><b>Python / Streamlit</b> (Dashboard)</li>
  <li><b>Pandas, Plotly</b> (Data manipulation & charts)</li>
  <li><b>Git / GitHub</b> (Version Control)</li>
</ul>

<hr>

<h2 id="project-structure">📁 Project Structure</h2>

<pre>
project/
│── BronzeLayer.sql
│── SilverLayer.sql
│── GoldLayer.sql
│── streamlit_app/
│     └── data.py
│── dashboards/
│     └── Streamlit Interface
│── README.md
</pre>

<hr>

<h2 id="setup--execution">🚀 Setup & Execution</h2>

<h3>1️⃣ Clone the Repository</h3>
<pre>git clone https://github.com/your-username/Financial-Reporting-Automation-Framework.git</pre>

<h3>2️⃣ Install Requirements</h3>
<pre>pip install -r requirements.txt</pre>

<h3>3️⃣ Run Streamlit Dashboard</h3>
<pre>streamlit run data.py</pre>

<hr>

<h2 id="data-quality--error-handling">✔ Data Quality & Error Handling</h2>
<ul>
  <li>Missing value detection</li>
  <li>Type validation</li>
  <li>Duplicate handling</li>
  <li>Transform-level integrity checks</li>
  <li>Error logging during ETL</li>
</ul>

<hr>

<h2 id="contribute">🤝 How to Contribute</h2>
<ol>
  <li>Fork the repository</li>
  <li>Create a feature branch</li>
  <li>Commit changes with proper messages</li>
  <li>Push and submit a Pull Request</li>
</ol>

<hr>

<h3 align="center">🎉 Thank You for Exploring the Financial Reporting Automation Framework!</h3>
