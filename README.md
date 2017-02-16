sprint
======
Results for [NEJM SPRINT Challenge](https://challenge.nejm.org/pages/home)

Authors: Mengyuan Kan, Edward Zhao, Brett Beaulieu-Jones, Blanca E Himes

### Lay Summary
SPRINT determined that treating individuals to have systolic blood pressure (SBP) near 120mmHg was better than 140mmHg. Although the average SBP of subjects within treatment groups differed, not all subjects had measures near their target. By grouping subjects according to actual SBP measures, rather than treatment group, we found that those with SBP >140mmHg were at increased risk for cardiovascular disease outcomes, while the risk of those with SBP 115-140mmHg was not substantially different.


### Extended Abstract
**Introduction.** The SPRINT Research Group conducted a clinical trial to determine whether a systolic blood pressure (SBP) target of 120mmHg (intensive treatment) would result in better health outcomes than the standard target of 140mmHg (standard treatment) among non-diabetic adults aged 50 or greater and at risk for cardiovascular disease (CVD). Within months of trial randomization, the mean SBP of subjects within each trial arm became significantly different, and as the trial proceeded, the composite CVD primary outcome and all-cause death rates were higher in standard vs. intensive treatment study arms. According to the SBP distribution of all subjects’ measures across the trial, however, some subjects had SPBs that were far from their target and, within portions of the 120-140 SBP range, substantial proportions of subjects from both arms were present. Our goal was to determine whether an ideal SBP target could be identified, not according to the SPRINT study arms, but by grouping subjects according to their actual SBP measures obtained during the trial. 

**Methods.** Statistical analyses were conducted with R software, including the survival package to create Cox proportional hazards regression models and obtain penalized spline basis functions. We used the median of all post-randomization SBP measures available for each individual (median trial SBP) to capture their SBP during the trial, as this value best reflects SBP from after treatment began until the last available observation and is robust to outlier measures. As outcome variables, we used the trial’s primary outcome variable and all-cause death. Penalized smoothing splines were obtained to assess variability in hazard ratios for each outcome vs. median trial SBP.

**Results.** According to the hazard ratio in spline models [Figures 1A and 1B], the log of the hazard ratio (logHR) for both the primary outcome and death were nearly constant for median trial SBP between 115 and 140 mmHg, and they rose sharply after 140 mmHg. Although the estimates were subject to more error for median trial SBP less than 115 mmHg, the logHR of death increased with decreasing median trial SBP values, while the logHR for primary outcome was nearly constant. Based on these regimes, three natural partitions of median trial SBP were <115, 115-140, and >140 mmHg. 
 
Cumulative hazards for the primary outcome computed according to these partitions showed that median trial SBP >140mmHg had a hazard ratio of 1.75 (95% CI 1.35-2.26; p-value 2.1x10-5) relative to the median trial SBP 115-140mmHg group, while there was no significant difference between the SBP 115-140 and <115 mmHg groups [Figure 1C]. Similarly, for all-cause death, cumulative hazards showed that median trial SBP >140mmHg had a hazard ratio of 2.27 (95% CI 1.68-3.06; p-value 8.4x10-8) relative to median trial SBP 115-140mmHg group, while there was no significant difference between the SBP 115-140 and <115 mmHg groups [Figure 1D]. 

Because most of the standard vs. intensive treatment subjects who were close to their target SBP were within the 115-140 mmHg group, we repeated the cumulative hazards computations with an additional partition of this group into median trial SBPs 115-130 and 131-140 mmHg. Relative to the 115-130mmHg group, the hazard ratios for the primary outcome and all-cause death were not significantly different for the \<115 or 131-140 mmHg groups. The \>140mmHg group continued to have elevated risk, and relative to the 115-130mmHg group, had a hazard ratio of 1.84 (95% CI 1.40-2.41; 1.1x10-5) for the primary outcome and 2.32 (95% CI 1.68-3.19; 2.5x10-7) for all-cause death.

**Figure 1.**
![](<./figs/Figure.png>)

**Conclusion.** Subjects whose median trial SBP was within 115-140mmHg had nearly the same primary outcome and all-cause death rates, while those with medial trial SBP >140mmHg had higher rates of events. Thus, while SPRINT suggests that an SBP target of 120mmHg was better than 140mmHg, a target greater than 120mmHg may be just as beneficial while requiring fewer medications.

### Description of files in repository 

SPRINTresults.rmd: An R markdown report that includes code that can be used to reproduce our results. To run the script, it should be under a sprint\_pop directory, otherwise an absolute path should be given. You will have to get the SPRINT dataset in order to run it, which requires a formal application to the NHLBI's [BioLINCC](https://biolincc.nhlbi.nih.gov/home/).

SPRINTresults.html: An html file corresponding to SPRINTresults.rmd. It can be downloaded to see a full report of our results that includes more details than those contained in the SPRINT abstract.

### Acknowledgements
Thank you to Ryan Urbanowicz, Casey Greene, Rebecca Hubbard, and Jason Moore for productive discussions related to this project.
