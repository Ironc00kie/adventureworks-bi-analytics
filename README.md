# AdventureWorks 2019 Business Intelligence Project

A comprehensive Business Intelligence solution built on the AdventureWorks2019 database, featuring ETL processes, multidimensional OLAP cubes, and interactive Power BI dashboards for sales and inventory analysis.

## 📊 Project Overview

This project implements a complete data warehousing and business intelligence pipeline, transforming transactional data from the AdventureWorks2019 database into actionable insights through dimensional modeling and interactive visualizations.

## 🏗️ Architecture

The solution is built using Microsoft's BI stack:

```
AdventureWorks2019 (OLTP)
         ↓
    SSIS ETL Processes
         ↓
   Data Warehouse (Star Schema)
         ↓
    SSAS OLAP Cubes
         ↓
   Power BI Dashboards
```

## 📁 Project Structure

```
adventureworks-bi-analytics/
│
├── Projet_AdventureWorks2019_CC_2425/      # SSIS ETL Project
├── Cube_AdventureWorks2019_CC_2425/        # SSAS Cube Project
└── Projet_AdventureWorks2019_CC_2425.pbix  # Power BI Report
```

## 🔧 Components

### 1. ETL Process (SSIS)

**Dimensions.dtsx**
- Extracts and transforms dimension data (Customer, Employee, Location, Product, Territory)
- Implements slowly changing dimensions (SCD) logic
- Data cleansing and validation

**Fact.dtsx**
- Loads fact tables for sales and inventory
- Maintains referential integrity with dimensions
- Handles incremental data loads

### 2. OLAP Cubes (SSAS)

**Sales Cube**
- Measures: Sales Amount, Quantity, Order Count, Profit Margin
- Enables multidimensional analysis across customer, product, geography, and time dimensions
- Pre-aggregated calculations for performance

**Inventory Cube**
- Measures: Stock Levels, Reorder Points, Inventory Value
- Supports inventory management and optimization
- Track product availability and movement

### 3. Dimensions

| Dimension | Key Attributes |
|-----------|---------------|
| **Customer** | Customer ID, Name, Demographics, Segments |
| **Employee** | Employee ID, Name, Department, Manager |
| **Location** | Geography hierarchy (Country → State → City) |
| **Product** | Product hierarchy (Category → Subcategory → Product) |
| **Territory** | Sales regions and territories |

### 4. Power BI Dashboard

Interactive visualizations providing:
- Sales performance analysis
- Inventory monitoring
- Trend analysis and forecasting
- KPI tracking and scorecards

## 🚀 Getting Started

### Prerequisites

- **SQL Server** (2017 or later) with AdventureWorks2019 database
- **SQL Server Integration Services (SSIS)** for Visual Studio
- **SQL Server Analysis Services (SSAS)** (Multidimensional mode)
- **Power BI Desktop**

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Ghorbel37/adventureworks-bi-analytics.git
   cd adventureworks-bi-analytics
   ```

2. **Restore AdventureWorks2019 database**
   - Download the AdventureWorks2019 backup file from Microsoft
   - Restore to your SQL Server instance

3. **Configure SSIS packages**
   - Open `Projet_AdventureWorks2019_CC_2425.sln` in Visual Studio
   - Update connection strings to point to your SQL Server
   - Deploy packages to SSIS Catalog

4. **Deploy SSAS cubes**
   - Open `Cube_AdventureWorks2019_CC_2425.sln` in Visual Studio
   - Update data source connections
   - Deploy to your SSAS server
   - Process cubes to load data

5. **Open Power BI dashboard**
   - Open `Projet_AdventureWorks2019_CC_2425.pbix` in Power BI Desktop
   - Update data source connections to your SSAS server
   - Refresh data

## 📈 Usage

### Running ETL Processes

Execute SSIS packages in the following order:
1. `Dimensions.dtsx` - Load all dimension tables
2. `Fact.dtsx` - Load fact tables

### Querying OLAP Cubes

Connect to SSAS using:
- Excel (PivotTables)
- SQL Server Management Studio (MDX queries)
- Power BI
- Any MDX-compatible client

### Viewing Dashboards

Open the Power BI file to explore:
- Sales dashboards by product, region, and time
- Inventory status and alerts
- Customer analysis and segmentation
- Employee performance metrics

## 🎯 Key Features

- ✅ **Complete ETL Pipeline**: Automated data extraction, transformation, and loading
- ✅ **Dimensional Modeling**: Star schema optimized for analytical queries
- ✅ **OLAP Cubes**: Fast multidimensional analysis with pre-aggregations
- ✅ **Interactive Dashboards**: User-friendly Power BI visualizations
- ✅ **Scalable Architecture**: Designed for enterprise-level data volumes

## 📊 Sample Analyses

The solution enables various analytical scenarios:
- Sales trends by product category and region
- Customer segmentation and profiling
- Inventory turnover and stock optimization
- Employee sales performance tracking
- Year-over-year comparisons and forecasting

## 🛠️ Technologies Used

- **ETL**: SQL Server Integration Services (SSIS)
- **Data Warehouse**: SQL Server
- **OLAP**: SQL Server Analysis Services (SSAS)
- **Visualization**: Power BI
- **Source Data**: AdventureWorks2019 OLTP database

## 📝 Notes

- This project was developed as part of a Data Visualization course
- Based on Microsoft's AdventureWorks2019 sample database
- Implements industry-standard dimensional modeling techniques
- Follows best practices for BI architecture and design

## 📄 License

This project is available for educational purposes. AdventureWorks database is a Microsoft sample database.

## 🔗 Resources

- [AdventureWorks Sample Databases](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure)
- [SSIS Documentation](https://learn.microsoft.com/en-us/sql/integration-services/)
- [SSAS Documentation](https://learn.microsoft.com/en-us/analysis-services/)
- [Power BI Documentation](https://learn.microsoft.com/en-us/power-bi/)
