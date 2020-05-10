# DO-LEFT-HANDED-PEOPLE-REALLY-DIE-YOUNG
## by Yueh-Han Chen
## Dataset

### Dataset Overview
<p>Barack Obama is left-handed. So are Bill Gates and Oprah Winfrey; so were Babe Ruth and Marie Curie. A <a href="https://www.nejm.org/doi/full/10.1056/NEJM199104043241418">1991 study</a> reported that left-handed people die on average nine years earlier than right-handed people. Nine years! Could this really be true? </p>
<p>In this notebook, I will explore this phenomenon using age distribution data to see if I can reproduce a difference in average age at death purely from the changing rates of left-handedness over time, refuting the claim of early death for left-handers. This notebook uses <code>pandas</code> and Bayesian statistics to analyze the probability of being a certain age at death given that you are reported as left-handed or right-handed.</p>
<p>A National Geographic survey in 1986 resulted in over a million responses that included age, sex, and hand preference for throwing and writing. Researchers Avery Gilbert and Charles Wysocki analyzed this data and noticed that rates of left-handedness were around 13% for people younger than 40 but decreased with age to about 5% by the age of 80. They concluded based on analysis of a subgroup of people who throw left-handed but write right-handed that this age-dependence was primarily due to changing social acceptability of left-handedness. This means that the rates aren't a factor of <em>age</em> specifically but rather of the <em>year you were born</em>, and if the same study was done today, I should expect a shifted version of the same distribution as a function of age. Ultimately, I'll see what effect this changing rate has on the apparent mean age of death of left-handed people, but let's start by plotting the rates of left-handedness as a function of age.</p>
<p>This notebook uses two datasets: <a href="https://www.cdc.gov/nchs/data/statab/vs00199_table310.pdf">death distribution data</a> for the United States from the year 1999 (source website <a href="https://www.cdc.gov/nchs/nvss/mortality_tables.htm">here</a>) and rates of left-handedness digitized from a figure in this <a href="https://www.ncbi.nlm.nih.gov/pubmed/1528408">1992 paper by Gilbert and Wysocki</a>. </p>

> Project from DataCamp

## File Explanation
- The ApplyBayesRule.ipynb is using Bayes Rule to investigate the question..
- The HypothesisTesting.ipynb is using Hypothesis Test to test the result we got from ApplyBayesRule.ipynb.

## Limitation and Result of ApplyBayesRule.ipynb

> Limitation 1: We used death distribution data from almost ten years after the study (1999 instead of 1991), and we used death data from the entire United States instead of California alone (which was the original study). 

> Limitation 2: We extrapolated the left-handedness survey results to older and younger age groups, but it's possible our extrapolation wasn't close enough to the true rates for those ages.

- Conclusion:
- Average dead age of right handedness: 72.81669680889921
- Average dead age of left handedness: 67.69702073317897
- Difference:  5.1196760757202355  years

## Result of HypothesisTesting.ipynb

> **H0: RH's average dead age - LH's average dead age == 9**

> **H1: RH's average dead age - LH's average dead age != 9**

- The p-value is  0.12209999999999999

I fail to reject the null hypothesis, because I don't have enough evidence to say that right-handed people average dead age minus right-handed people's dead age is not equal to 9 years.
