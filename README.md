## Overview

**royal-mail-shopify** is a Rstudio data wrangling script for joining Royal Mail Click & Drop manifest data with Shopify order data.
The purpose of this script is to help identify the profitability of Shopify shipping charges in relation to Royal Mail Click & Drop charges. 

It uses the **tidyverse** to pull in two CSV files, clean them, collate them and then join them to output a new CSV file. 
The resultant file can then identify profit/loss in your Shopify shipping charges.

## Installation

There are two dummy CSV files in the data directories that will need to be replaced with live data.
One file will be the CSV export of Shopify orders to be placed in the orders data folder.
One file will be the CSV export of the Royal Mail Click & Drop manifest charges to be placed in the manifest data folder 
