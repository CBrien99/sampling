# Assignment: Questionnaire Design and Sample Evaluation

## Requirements

The goal of this assignment is to practice developing and evaluating sampling materials.

### Part A - Survey Design:

Select one of the scenarios below and design a survey to meet the need(s) outlined in the prompt.

1.	In two to three sentences, describe the purpose of your survey
2.	Describe your target population, sampling frame, sampling units, and overall sampling strategy.
3.	Write a 5-10 question survey to address your chosen scenario below.

##### Scenarios
1.	You work in the Human Resources Department at a large tech company. Over the past few months, the company has been experiencing a high turnover rate across many of its departments, specifically within the entry- and lower-level positions. The company wishes to understand why this turnover is happening, and what changes need to occur to improve employee satisfaction.
2.	You work for a Canadian national political party during a federal election. Throughout the campaign period, your party has seen relatively high approval ratings, but an opposing party is also polling favorably and may still have a chance to win the election. You are one month away from the election and you want to understand what voters want from your party and its leader in order to maintain your lead and eventually win the election.
3.	You are a student researcher in the sociology department at the University of Toronto. You are working on a research project that concerns the relationship between music taste and age. This involves both comparisons between different people of different ages and comparisons of the same individual at different ages during their lifetime. You wish to understand to what extent age influences music taste, specifically as it relates to perceptions of popular music. Your results will be written into an academic paper that you hope to publish.

### Part B - Survey Evaluation:

For the **Canadian General Social Survey on Giving, Volunteering, and Participating, 2018 (cycle 33)**, conducted by Statistics Canada find any and all available documentation for the data gathered and identify and describe the survey features indicated below.

1. Sample type
2. Sample size
3. Target population
4. Sampling frame
5. Survey mode(s) 
6. Timeline
7. Response rate
8. Weights
9. Data processing
10. Cleaning, imputation, etc
11. Sources of error
12. Limitations, known biases, etc
13. Link to documentation and any additional sources used


# Your Changes

## Part A - Survey Design: 

The number of your chosen topic: `2`

Describe the purpose of your survey:

```
The purpose of this survey is to identify the key issues, values, and leadership qualities that matter most to Canadian voters in the final month leading up to the federal election. By understanding voter priorities and perceptions of the party’s performance, the survey will inform strategic decisions to maintain public support and secure an election win.

```

Describe your target population, sampling frame, sampling units, and observational units:
```
Target Population: Eligible Canadian voters across all provinces and territories who intend to vote in the upcoming federal election.

Sampling Frame: A compiled list of registered voters from Elections Canada, supplemented by national polling panels and phone/email directories to ensure broader coverage.

Sampling Units: Individual registered voters selected from the sampling frame.

Observational Units: The same individual voters who respond to the survey and provide information on their preferences, concerns, and political attitudes.
```

Your 5-10 question survey:
```
1. Which federal political party do you currently support or lean toward supporting?
2. How likely are you to vote in the upcoming federal election?
3. How would you rate the performance of the current government?
4. How trustworthy do you find the leader of our party?
5. Which of the following best describes your political engagement?
6. Have your opinions about our party changed over the past month?
7. What is your age group?

```

## Part B - Survey Evaluation:

Identify and describe survey features:

```
1. Sample type:
    Probability sample using stratified sampling and rejective sub-sampling. One respondent aged 15+ per household was randomly selected. Volunteers were oversampled using longer interviews; non-volunteers were split into short or long interview groups.
2. Sample size
   A field sample of approximatively 50,000 units was used. Among them, about 40,000 invitation letters to the electronic questionnaire were sent to selected households across Canada. A completion of 24,000 questionnaires was expected.
3. Target population
    Persons aged 15 and older living in private households in the ten Canadian provinces.
    Excludes: residents of territories and institutionalized individuals.
4. Sampling frame
    A blended sampling frame was used, incorporating both landline and mobile telephone numbers. These were derived from Statistics Canada’s dwelling frame, which is informed by census data and administrative records.
5. Survey mode(s) 
    - A stratified random sampling design was implemented, where stratification occurred by province and census metropolitan area (CMA). One person aged 15+ was randomly selected from each household, with no proxy respondents permitted.
    - Once the minimum sample size for each province was achieved, additional sample allocation was optimized to balance precision needs for both national and regional estimates.
    - A rejective sub-sampling approach was used after determining if respondents volunteered. All volunteers completed a full questionnaire, while non-volunteers were split into two groups: one completing the full questionnaire, the other a shortened version.)
6. Timeline
    Data collection took place from September 4 to December 28, 2018.
7. Response rate
    The overall response rate was 41.9%.
8. Weights
    - Each respondent was assigned a weight representing how many people in the population they stand in for (e.g., 1:50).
    - These weights were adjusted to ensure alignment with 2017 Canadian Income Survey (CIS) distributions by province.
    - Bootstrap weights were also created to allow for accurate variance estimation.
9. Data processing
    Processing followed Statistics Canada's Social Survey Processing Environment (SSPE), which uses standardized tools and workflows.
10. Cleaning, imputation, etc
    - IBoth automated and manual checks were conducted at multiple stages.
    - Family structure and matrix data were reviewed for logical consistency.
    - Logical flows were validated to ensure respondents answered relevant questions.
    - CATI system-based error detection and corrections were implemented during interviews.
11. Sources of error
    - Sampling error: Differences between sample estimates and true population values.
    - Non-sampling errors: Issues like incomplete coverage of the population and non-response.
    - Response error: Inaccurate answers from respondents.
    - Processing error: Mistakes during data handling or processing.
12. Limitations, known biases, etc
   - Exclusion of territories and institutionalized populations may reduce generalizability.
   - Self-reporting may introduce social desirability or recall bias.
   - Mode effects (e.g., differences in responses between CATI and EQ).
13. Link to documentation and any additional sources used
- https://www23.statcan.gc.ca/imdb/p2SV.pl?Function=getSurvey&Id=796234
- https://www23.statcan.gc.ca/imdb/p3Instr.pl?Function=getInstrumentList&Item_Id=1183690&UL=1V&

```

## Rubric

-	All required components are present and complete **Complete / Incomplete**
-	Choice of sampling strategy for Part A is justified and related to survey purpose **Complete / Incomplete**
-	Information for Part B is complete and correct **Complete / Incomplete**

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 18/04/2025`
* The branch name for your repo should be: `assignment-2`
* What to submit for this assignment:
    * This markdown file (a2_survey_design_and_evaluation.md) should be populated and should be the only change in your pull request.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [X] Create a branch called `assignment-2`.
- [X] Ensure that the repository is public.
- [X] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [X] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
