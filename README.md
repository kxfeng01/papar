# Extracting Wage Information from Unstructured Job Postings
## Purpose
This project aims to extract wage information from the unstructured text of job postings to study the impact of Colorado’s pay transparency law on patterns of wage disclosure. The job posting data used in this project is provided by [LinkUp](https://www.linkup.com/), a leading data provider that sources job postings from company websites.

## Approach
I use a three-step approach for wage extraction: 

1. Isolating Text Segments Containing Wage Data
2. Fine-Tuning a Question-Answering Transformer Model
3. Extracting and Categorizing Wage Figures Using Regular Expressions

## Challenges and Solutions

1. **Limited access to large LLMs**
    * Challenge: As a student, I did not have the computing resources or funding to use commercial LLMs.
    * Approach: I chose **smaller, open-source transformers** that could be fine-tuned on university machines.
2. **Unstructured job posting text**
    * Challenge: Salary details were buried in a variety of unstructured text (hourly rates, annual salaries, ranges, etc.).
    * Approach: I **filtered chunks of text** likely to contain wage information, such as those with a dollar sign followed by digits (e.g., $12, $9, $52,000), from job descriptions.
3. **Data Annotation and Fine-Tuning**
    * Challenge: Manually labeling wage snippets is time-consuming and error-prone.
    * Approach: I used **semi-automatic labeling** by first using a **pre-trained transform model** to identify likely wage snippets, then manually correcting them to construct a high-quality training set.
4. **Diverse wage formats**
    * Challenge: Wage data appeared in multiple formats - hourly, annual, ranges.
    * Approach: I used **regular expressions** to parse numeric patterns and pay frequency indicators, categorized wages by pay frequency (hourly/monthly/biweekly/annually), and annualized the extracted numbers.
5. **Hardware and computational limitations**
    * Challenge: With a dataset of over 1 billion records, running predictions on a single machine was slow - it would take several days.
    * Approach: I **split the dataset** into smaller portions and **ran them in parallel** on multiple processes, which took only a few hours to complete.

## Model Evaluation
The finetuned model significantly outperforms the base model, achieving an exact match rate of **88.05%** and an F1 score of **93.76%**, compared to the original rates of 54.08% and 66.39%, respectively.

## Further Insights
The findings and analyses using the extracted wage data are available in the working paper "Pay Transparency and Gender Differences in Job Search" at https://dx.doi.org/10.2139/ssrn.4984519.

Author: Kexin Feng
