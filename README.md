# Extracting Wage Information from Unstructured Job Postings
## Purpose
This project aims to extract wage information from the unstructured text of job postings to study the impact of Colorado’s pay transparency law on patterns of wage disclosure. The job posting data used in this project is provided by [LinkUp](https://www.linkup.com/), a leading data provider that sources job postings from company websites.

## Approach
I use a three-step approach for wage extraction: 

1. Isolating Text Segments Containing Wage Data
2. Fine-Tuning a Question-Answering Transformer Model
3. Extracting and Categorizing Wage Figures Using Regular Expressions

## Evaluation
The finetuned model significantly outperforms the base model, achieving an exact match rate of 88.05% and an F1 score of 93.76%, compared to the original rates of 54.08% and 66.39%, respectively.

## Further Insights
The findings and analyses using the extracted wage data are available in the working paper "Pay Transparency and Gender Differences in Job Search" at https://dx.doi.org/10.2139/ssrn.4984519.

Author: Kexin Feng
