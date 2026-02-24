# My DTSC-2301 Blog

Project 1: Defining a Data Science Problem & Understanding Data write up

Problem statement:
For the project, I’m asking if there is any correlation between students taking advantage of in-school support systems and improved academic performance.
I’ve always been interested in how education systems operate and support at-risk students, especially as a returning student. I believe this will be of interest to a wide range of people, from struggling students to academic faculty who seek to reduce the attrition rate and meaningfully deploy students into the job market with the best chance of success.
I am neither criticizing nor praising education systems, nor am I seeking to make suggestions. I only intend to create a product that will better inform a reader of how participation in in-school support systems relates to academic performance.

Dataset Description
For the project, I selected a dataset compiled by Paulo Cortez in 2008 regarding the academic performance of 649 Portuguese students. The dataset is observational, and participation was not randomly assigned.
Each row represents a student’s academic profile and includes 33 separate data points. The key variables I focused on were the student’s gender and age, categorized study-time, number of previously failed classes, whether the student intended to attend further schooling after secondary school, absences, participation in in-school support, whether the student’s family supported them academically, and their first, second and final report cards (based on a 20-point scale) in a given year.
The dataset itself was found on Kaggle.com via the UCI Machine Learning Repository.

Data Cleaning & Preparation:
The initial dataset had 33 variables, 21 of which were deemed outside of scope, either due to being irrelevant to the problem statement (like a student’s daily/weekly alcohol consumption, parental status, etc.) or may have served to complicate the scope of the problem (like a student’s address, parental status, mother/father’s job/education level, etc.) The remaining 12 all potentially had a meaningful relationship with in-school support program attendance and final grades.
For the modified dataset, grades were handled on a numeric scale (0-20). Very little data modification needed to happen, as relationships were examined between numerical variables (G1, G2, G3) and a categorical binary (“schoolsup” yes/no).
There were no null values in the dataset, no variable normalization was required, and there was no random assignment. It was assumed that G3 reflects overall academic performance and that growth approximates improvement. It was also assumed that the timing for when in-school support participation began was unknown.


Findings 
While investigating the dataset, I focused primarily on comparing the performance of the groups that received school support and those who did not: the difference in final grade (G3) between students who did receive school support (which I will be referring to as S+G) and did not receive school support (S-G), the high/low values per each category, and the degree of improvement.
Overall, the difference between the final grades was negligible: When comparing the growth from G1 to G3 for S+G, we see an average increase of only .45 points. When examined along the same axis, S-G grew by .51 points, for a relative difference of only .06 points. A similar trend emerges when comparing just the final grades of both groups: S-G had an average final grade that was ~.7 points higher than S+G. Despite seeming to be far more substantial than the earlier metric, neither of these clearly indicates whether the school support system is helpful due to factors that will be discussed later. 
Initially, I planned to use a grouped bar chart to compare the before- and after-grades for the two groups, but found very little value, so I pivoted to examining the big 5 values. When examining the box plots for student performance, another pattern became apparent: The median grade of the two groups is comparable, but the lower bounds and upper bounds for S+G are much tighter than those of S-G. While this is evidence that might suggest school support has a positive impact on student’s final grades, it’s worth considering the overall sample size for the groups: The total survey was 649 students, and only 68 of them received school support. This will naturally yield narrower results and make the presence of outliers more pronounced.

Constraints
There were several issues with the data set: age of the data, information not captured, potential biases in participants, and potential ethical concerns.
Any conclusions from the dataset may not be easily applied to American education systems, as it was created 17-18 years ago, and was taken by students belonging to either of two Portuguese schools. It also did not identify when S+G began receiving support, and it did not discuss how intense the support each student received.
Additionally, the dataset itself is subject to bias: due to remarkably few students receiving support taking the survey as well as the average G3 being ~12 and lack of clear random sampling/intervention timing, causal interpretation is ultimately not possible.
Finally, there are several ethical concerns regarding the use of the dataset. There is potential for the dataset to be used to argue for reduced school funding with the interpretation that school support does not make a difference. While the exploration did not prove that it did help, it also did not prove that it did not. Additionally, the simplification of varying factors into a final numerical grade undercuts the nuance that informs each G3 entry. Finally, there is a risk of stigmatizing students who did not succeed, or who have factors in their lives wholly separate from school that may be affecting them, such as parental relationship status or income.

Code
https://github.com/rshea4-hub/DTSC-2301/blob/main/Project1Submission.ipynb

References & AI Use Transparency
Dataset link: Student Performance Data Set
In creating this project, I repeatedly googled python functions (dropping columns, ALL the code to make grouped bar charts, that was awful, labeling box plots, etc.) and relied on ChatGPT for grammar and structure (i.e. reorganizing sentences in a paragraph for coherence).
ChatGPT conversation: Project Planning for Data Science

