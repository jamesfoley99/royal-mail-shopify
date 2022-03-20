## Overview

**royal-mail-shopify** is a Rstudio data wrangling script for joining Royal Mail Click & Drop manifest data with Shopify order data.
The purpose of this script is to help identify the profitability of Shopify shipping charges in relation to Royal Mail Click & Drop charges. 

It uses the **tidyverse** to pull in two CSV files, clean them, collate them and then join them to output a new CSV file. 
The resultant file can then identify profit/loss in your Shopify shipping charges.

## Preparation

There are two dummy CSV files in the data directories that will need to be replaced with live data.
One file will be the CSV export of Shopify orders to be placed in the orders data folder.
One file will be the CSV export of the Royal Mail Click & Drop manifest charges to be placed in the manifest data folder 

This script calls the tidyverse so you will have to install it if it is not already in your Rstudio install

``` r
# To install the latest version:
install.packages("tidyverse")
```
## Working with royal-mail-shopify

This script uses the Royal Mail prices as of April, 2022.
These prices are placed in vectors at the start of the script and will need to be updated for any price increases

``` r
# Royal Mail prices inc VAT
# weights listed in (g)
large_letter = list("100g"=c("1.37","1.08"),"250g"=c("1.94","1.48"),"500g"=c("2.11","1.70"),"750g"=c("2.75","2.22"))
parcel = list("1000g"=c("4.06","3.07"),"2000g"=c("4.30","3.43"),"10000g"=c("7.14"),"20000g"=c("13.14"))
sdg_wd = list("100g"=c("7.50"),"500g"=c("7.86"),"1000g"=c("9.18"),"2000g"=c("11.70"),"10000g"=c("16.14"))
sdg_we = list("100g"=c("10.50"),"500g"=c("10.86"),"1000g"=c("12.18"),"2000g"=c("14.70"),"10000g"=c("19.14"))
```

This script will write to a CSV file currently called manifest_dump.csv

```{r}
write_csv(manifest_dump,"manifest_dump.csv")
```

