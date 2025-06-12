# Nashville Housing Data
This Repository contains files that have been used for my portfolio projects. Feel free to check them out, and please reach out if you have any questions and/or inquiries.

**Project Overview**

This project focused on cleaning and transforming a raw housing dataset from Nashville to prepare it for accurate analysis and reporting. The dataset contained inconsistencies, missing values, formatting issues, and redundant columns—all of which were addressed using SQL-based techniques.

**Goals**
- Standardize and clean messy or missing data fields.
- Break down composite fields (like addresses) into usable components.
- Eliminate inconsistencies and duplicates.
- Optimize the dataset structure for future analysis or dashboard integration.

**Key Steps and Techniques
Date Format Standardization:**
- Converted inconsistent date values in the SaleDate column to SQL Date format.
- Created a new SaleDateConverted column to preserve and standardize date values.
- Filling Missing Property Address Values:
- Identified records with missing PropertyAddress values.
- Used self-joins on ParcelID to find matching addresses from duplicate records.
- Populated null values with the correct data using ISNULL().

**Address Normalization:**

- Split the PropertyAddress column into two new fields: PropertySplitAddress and PropertySplitCity using SUBSTRING() and CHARINDEX().
- Separated the OwnerAddress field into OwnerSplitAddress, OwnerSplitCity, and OwnerSplitState using PARSENAME() after replacing commas.

**Data Consistency:**

- Standardized SoldAsVacant values by replacing 'Y' and 'N' with 'Yes' and 'No' using a CASE statement.
- Duplicate Detection and Removal:
- Created a CTE with ROW_NUMBER() to identify exact duplicate records based on key fields like ParcelID, SalePrice, and LegalReference.
- Filtered out rows with row_num > 1 for potential deletion.

**Schema Optimization:**

- Dropped irrelevant or redundant columns including OwnerAddress, TaxDistrict, and PropertyAddress.
- Removed SaleDate after standardizing and replacing it with SaleDateConverted.

**Outcome**

- Produced a clean, normalized housing dataset suitable for market analysis, visualization, or modeling.
- Resolved nulls and formatting issues that would otherwise lead to inaccurate insights.
- Improved data integrity, making the dataset more scalable and reliable for downstream uses.

**What I Learned**
- How to apply SQL for real-world data cleaning tasks.
- Effective use of CTEs and string functions for field decomposition.
- Best practices for preparing data tables for business intelligence tools and analysis.
