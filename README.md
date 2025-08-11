# Glassdoor Reviews EDA
## Description
Glassdoor is an American website where current and former employees anonymously review companies, operated by the company of the same name. Glassdoor launched its company ratings site in June 2008, and since then it produces reports based upon the data collected from its users, on topics including work–life balance, CEO pay-ratios, lists of the best office places and cultures, and the accuracy of corporate job searching maxims.

The aim of this project is to explore a reviews dataset covering the period from 2008 to 2021. The data then will be proccessed and cleaned to perform a basic Exploratory Data Analysis.


## Dataset
The dataset is large, and it contains job descriptions and rankings among various criteria such as work-life balance, income, culture, etc. The data covers the various industries in the UK. Source: [Click here]("https://www.kaggle.com/datasets/davidgauthier/glassdoor-job-reviews")

The columns correspond to the date of the review, the job name, the job location, the status of the reviewers, and the reviews. Reviews are divided in s sub-categories Career Opportunities, Comp & Benefits, Culture & Values, Senior Management, and Work/Life Balance. In addition, employees can add recommendations on the firm, the CEO, and the outlook.

### Data Dictionary
<table style="width: 100%; border-collapse: collapse; background-color: #fff;">    
    <thead>
        <tr>
            <th style="background-color: #3498db; text-align: left; padding: 8px;">Feature</th>
            <th style="background-color: #3498db; text-align: left; padding: 8px;">Definition</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="padding: 8px;">Firm (str)</td>
            <td style="padding: 8px;">Name of the company being reviewed</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Date Review (str)</td>
            <td style="padding: 8px;">Date the review was submitted</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Job Title (str)</td>
            <td style="padding: 8px;">Job title of the reviewer</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Employment Status (str)</td>
            <td style="padding: 8px;">Employment status: whether the reviewer is a current or former employee</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Location (str)</td>
            <td style="padding: 8px;">Geographic location of the job being reviewed</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Overall Rating (int)</td>
            <td style="padding: 8px;">Overall rating of the company on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Work-Life Balance (int)</td>
            <td style="padding: 8px;">Rating of the company's support for work-life balance on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Culture & Values (int)</td>
            <td style="padding: 8px;">Rating of company culture and core values on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Diversity & Inclusion (int)</td>
            <td style="padding: 8px;">Rating of the company’s commitment to diversity and inclusion on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Career Opportunities (int)</td>
            <td style="padding: 8px;">Rating of the availability of career advancement opportunities on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Compensation & Benefits (int)</td>
            <td style="padding: 8px;">Rating of compensation (salary) and benefits (insurance, perks, etc.) on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Senior Management (int)</td>
            <td style="padding: 8px;">Rating of the quality and trust in senior leadership/management on a scale from 1 (worst) to 5 (best)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Recommend to Friend (str)</td>
            <td style="padding: 8px;">Whether the employee would recommend the company to a friend (positive/mild/negative/no opinion)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">CEO Approval (str)</td>
            <td style="padding: 8px;">Whether the employee approves of the CEO’s leadership (positive/mild/negative/no opinion)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Outlook (str)</td>
            <td style="padding: 8px;">The employee’s outlook on the future of the company (positive/mild/negative/no opinion)</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Headline (str)</td>
            <td style="padding: 8px;">Title or summary line of the review</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Pros (str)</td>
            <td style="padding: 8px;">Positive aspects of the job or company, written by the reviewer</td>
        </tr>
        <tr>
            <td style="padding: 8px;">Cons (str)</td>
            <td style="padding: 8px;">Negative aspects or criticisms, written by the reviewer</td>
        </tr>
    </tbody>
</table>


## Analysis
The goal of this EDA is to solve the following probelms:
<ol>
    <li>What is the distribution of overall ratings?</li>
    <li>What is the average rating across all companies?</li>
    <li>Which companies have the highest and lowest average ratings?</li>
    <li>What are the average scores for:</li>
    <ul>
        <li>Work-life balance</li>
        <li>Culture and values</li>
        <li>Career opportunities</li>
        <li>Compensation and benefits</li>
        <li>Senior management</li>
    </ul>
    <li>Which job titles have the highest and lowest average ratings?</li>
    <li>How do the top 5 most-reviewed companies compare in each of the sub-ratings?</li>
    <li>Which company has the highest positive recommendation percentage?</li>
    <li>Is there a correlation between overall rating and recommend?</li>
    <li>What is the proportion of current and former employees in the dataset?</li>
</ol>

A sample of 577,992 reviews from 2008 to 2021 has been analyzed. 59.6% of the reviewers are current employees, whereas 40.4% are former employees. The overall rating has a mean of 3.65. The sub-ratings covers 5 main aspects: work-life balance, culture and values, career opportunities, compensation and benefits, and senior management, and have a mean of 3.4, 3.6, 3.5, 3.4 and 3.2, respectively. 

### Important Notes
-	Although we can extract trends over time and regional differences using the <code>date_review</code> and <code>location</code> columns, we are not aiming to analyze time and geography. Hence, and for the sake of simplicity of this project, we will be ignoring those columns.
-	The <code>diversity_inclusion</code> rating column will be dropped off the dataset as it is missing 84% values. The company has added this rating by the mid of 2020, which only covers a small portion of our dataset.
-	We are not aiming to process open text questions and extract insights from written words, and hence the <code>headline</code>, <code>pros</code>, and <code>cons</code> columns will be ignored.
-	With the selected columns that we will be working on, it was decided that any row with missing value will be dropped. Such data like ratings cannot be imputed or auto filled.

### Future Improvements
-	Explain how ratings vary by location.
-	Extract insights about the average rate plot over time.
-	Find the most common pros and cons for each firm.

  
## How to Run
- Clone repo
<code>git clone https://github.com/yourusername/your-repo-name.git</code>
<code>cd your-repo-name</code>

- Install dependencies
<code>pip install pandas numpy seaborn matplotlib jupyter</code>

- Launch notebooks
<code>jupyter notebook notebooks/Exploration.ipynb</code>
<code>jupyter notebook notebooks/Analysis.ipynb</code>


## Dependencies
pandas, numpy, matplotlib, seaborn, 

