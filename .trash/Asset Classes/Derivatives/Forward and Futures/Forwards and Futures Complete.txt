---
aliases:
- Alias_260_Forwards and Futures Complete.md
- FORWARDS AND FUTURES COMPLETE
- Alias_263_Forwards and Futures Complete.md
linter-yaml-title-alias: FORWARDS AND FUTURES COMPLETE
tags:
- 1
- tag_example
title: Forwards and Futures Complete
---



# Forwards and Futures Complete

1 The Oregon Health Insurance Experiment,  Revisited
In this problem,  you will continue to work with the data from Problem Set #1
For this assignment,  you can refer to any output that comes from the lm() function in R.

1. In Problem Set Q2.1,  we found that one of the baseline characteristics,  numhh list,  was statistically significant from zero at the 5 percent level. Oh no,  [DiD](Lecture%2013-%20Difference-In-Differences%20(Part%202%20Of%202).md) randomization fail? It turns out that the researchers expected this. The reason this happened is because treatment was assigned at the household level,  and households with more eligible individuals had more chances to win the lottery. Fortunately,  we can easily deal with this violation of balance using [Multivariate Regression](Multivariate%20OLS.md) techniques!
The regression controlling for family size is given as follows:$$Y=\beta_0+\beta_1Treated+\beta_2numhh_list+u \tag{1}$$Recall in problem set$\#1$,  you ran the following regression:$$Y=\beta_0^{\prime}+\beta_1^{\prime}Treated+v \tag{2}$$
For each of the five outcomes,  calculate the bias from not including numhh list as a control,  filling in the table below. Are any of these biases quantitatively large enough to fundamentally change any of your qualitative conclusions about the OHIE? 

| Variable | Bias |
| ---- | ---- |
| count_visit_dr | 0.197818<br> |
| count_visit_er | 0.038145<br> |
| out_of_pocket_spend | 5.841552<br> |
| health_score | 0. 002062<br> |
| happy | - 0. 007312 |

> [!NOTE]
> The biases for these outcomes are unlikely to change the qualitative conclusions of OHIE,  since none are larger than the treatment effects themselves. WHile the bias on out of pocket spend may appear big,  it must be noted that the coefficient on beta for the model without the control was -73.044184$abd for the model with the control was -67.202631$. Thus,  the bias is not that large in this context.

|          | Outcome             | Beta_1_<br>Without_Control | SE_Without<br>_Control | Beta1_With<br>_Control | SE_With<br>_Control | Bias       |
| -------- | ------------------- | -------------------------- | ---------------------- | ---------------------- | ------------------- | ---------- |
| treated  | count_visit_dr      | 0.39569188                 | 0.21597851             | 0.59351024             | 0.21657276          | 0.19781837 |
| treated1 | count_visit_er      | -0.0358896                 | 0.03550025             | 0.00225535             | 0.03556036          | 0.03814492 |
| treated2 | out_of_pocket_spend | -73.044184                 | 21.8272026             | -67.202631             | 21.9456196          | 5.8415524  |
| treated3 | health_score        | -0.0015582                 | 0.0015358              | 0.00050426             | 0.00153556          | 0.00206248 |
| treated4 | happy               | 0.01237267                 | 0.00782441             | 0.00506072             | 0.0078449           | -0.007312  |

```latex
> setwd("/Users/rogerlin/Desktop/Desktop - Roger’s MacBook Air/Harris MPP Year 2 /Stats II/Stats II PSET III")
> ohie_data <- read.csv("OHIE.csv")
>
> model <- lm(count_visit_dr ~ treated + numhh_list,  data = ohie_data)
> 
> result <- summary(model)
> 
> print(result)
>
Call:
lm(formula = count_visit_dr ~ treated + numhh_list,  data = ohie_data)

Residuals:
    Min      1Q  Median      3Q     Max 
 -6.760  -5.760  -3.760  -0.028 137.834 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   8.3039     0.3368  24.658  < 2e-16 ***
treated       0.5935     0.2166   2.740  0.00614 ** 
numhh_list   -2.1378     0.2495  -8.567  < 2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 11.86 on 12155 degrees of freedom
  (71 observations deleted due to missingness)
Multiple R-squared:  0.006276, 	Adjusted R-squared:  0.006113 
F-statistic: 38.38 on 2 and 12155 DF,   p-value: < 2.2e-16

> outcomes <- c("count_visit_dr",  "count_visit_er",  "out_of_pocket_spend",  "health_score",  "happy")
> 
> outcome <- "count_visit_dr"
> model_without_control <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
> beta1_without_control <- coef(model_without_control)["treated"]
> se_without_control <- summary(model_without_control)$coefficients["treated",  "Std. Error"]
> model_with_control <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
> beta1_with_control <- coef(model_with_control)["treated"]
> se_with_control <- summary(model_with_control)$coefficients["treated",  "Std. Error"]
> bias <- beta1_with_control - beta1_without_control
> 
> cat("Beta1 With Control:",  beta1_with_control,  "SE:",  se_with_control,  "\n")
Beta1 With Control: 0.5935102 SE: 0.2165728 
> outcome <- "count_visit_er"
> model_without_control_er <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
> beta1_without_control_er <- coef(model_without_control_er)["treated"]
> se_without_control_er <- summary(model_without_control_er)$coefficients["treated",  "Std. Error"]
> model_with_control_er <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
> beta1_with_control_er <- coef(model_with_control_er)["treated"]
> se_with_control_er <- summary(model_with_control_er)$coefficients["treated",  "Std. Error"]
> bias_er <- beta1_with_control_er - beta1_without_control_er
> 
> outcome <- "out_of_pocket_spend"
> model_without_control_oop <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
> beta1_without_control_oop <- coef(model_without_control_oop)["treated"]
> se_without_control_oop <- summary(model_without_control_oop)$coefficients["treated",  "Std. Error"]
> model_with_control_oop <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
> beta1_with_control_oop <- coef(model_with_control_oop)["treated"]
> se_with_control_oop <- summary(model_with_control_oop)$coefficients["treated",  "Std. Error"]
> bias_oop <- beta1_with_control_oop - beta1_without_control_oop
> 
> outcome <- "health_score"
> model_without_control_hs <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
> beta1_without_control_hs <- coef(model_without_control_hs)["treated"]
> se_without_control_hs <- summary(model_without_control_hs)$coefficients["treated",  "Std. Error"]
> model_with_control_hs <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
> beta1_with_control_hs <- coef(model_with_control_hs)["treated"]
> se_with_control_hs <- summary(model_with_control_hs)$coefficients["treated",  "Std. Error"]
> bias_hs <- beta1_with_control_hs - beta1_without_control_hs
> 
> outcome <- "happy"
> model_without_control_happy <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
> beta1_without_control_happy <- coef(model_without_control_happy)["treated"]
> se_without_control_happy <- summary(model_without_control_happy)$coefficients["treated",  "Std. Error"]
> model_with_control_happy <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
> beta1_with_control_happy <- coef(model_with_control_happy)["treated"]
> se_with_control_happy <- summary(model_with_control_happy)$coefficients["treated",  "Std. Error"]
> bias_happy <- beta1_with_control_happy - beta1_without_control_happy
> 
> cat("Bias:",  bias,  "\n")
Bias: 0.1978184 
> cat("Bias for count_visit_er:",  bias_er,  "\n")
Bias for count_visit_er: 0.03814492 
> cat("Bias for out_of_pocket_spend:",  bias_oop,  "\n")
Bias for out_of_pocket_spend: 5.841552 
> cat("Bias for health_score:",  bias_hs,  "\n")
Bias for health_score: 0.00206248 
> cat("Bias for happy:",  bias_happy,  "\n")
Bias for happy: -0.007311952
```

```latex
> outcomes <- c("count_visit_dr",  "count_visit_er",  "out_of_pocket_spend",  "health_score",  "happy")
> 
> results <- data.frame(Outcome = character(),  
+                       Beta1_Without_Control = numeric(),  
+                       SE_Without_Control = numeric(), 
+                       Beta1_With_Control = numeric(),  
+                       SE_With_Control = numeric(),  
+                       Bias = numeric(), 
+                       stringsAsFactors = FALSE)
> for (outcome in outcomes) {
+     model_without_control <- lm(as.formula(paste(outcome,  "~ treated")),  data = ohie_data)
+     beta1_without_control <- coef(model_without_control)["treated"]
+     se_without_control <- summary(model_without_control)$coefficients["treated",  "Std. Error"]
+     model_with_control <- lm(as.formula(paste(outcome,  "~ treated + numhh_list")),  data = ohie_data)
+     beta1_with_control <- coef(model_with_control)["treated"]
+     se_with_control <- summary(model_with_control)$coefficients["treated",  "Std. Error"]
+     bias <- beta1_with_control - beta1_without_control
+     results <- rbind(results,  data.frame(Outcome = outcome, 
+                                          Beta1_Without_Control = beta1_without_control, 
+                                          SE_Without_Control = se_without_control, 
+                                          Beta1_With_Control = beta1_with_control, 
+                                          SE_With_Control = se_with_control, 
+                                          Bias = bias))
+ }
> print(results)
> 
```

---

1. Let’s look at which groups increased their doctor office visits the most in response to the treatment. Fill in the table below by running separate regressions of visit dr on treated,  and controlling for numhh list,  i.e. by running model (1) above,  for each of the groups listed in the table. Discuss your findings: which group has the largest estimated treatment effects,  which group has the smallest? Be sure to also consider the statistical significance. (3 points)

| Variable |$\hat{\beta}_1$| S.E.($\hat{\beta}_1)$|
| ---- | ---- | ---- |
| female == 0 | 0.342039 | 0.283625 |
| female == 1 | 0.792638 | 0.311858 |
| age < 50 | 0.644045 | 0.258844 |
| age ≥ 50 | 0.409736 | 0.393366 |
| race_white == 0 | 0.163863 | 0.330305 |
| race_white == 1 | 0.806660 | 0.276011 |
| health_baseline == 0 | 0.645016 | 0.239367 |
| health_baseline == 1 | 0.418033 | 0.468109 |
|  |  |  |

> [!NOTE]
> - The group with the largest estimated treatment effect is race_white == 1,  or non-Hispanic Whites,  with an increase of approximately 0.807 visits. This effect is statistically significant given the standard error of 0.276 (0.807>0.276). The race_white == 0,  or non-White group has the smallest estimated treatment effect,  which is about 0.164 visits more. However,  this effect is not statistically significant given the relatively large standard error of 0.33. Female individuals (female == 1) also show a significant increase in doctor visits compared to male individuals (female == 0). The increase is about 0.79,  which is significant as the SE coefficient is 0.311. Younger individuals (age < 50) exhibit a larger increase in doctor visits (increase of 0.644 visits,  which is significant since SE is 0.258) than older individuals (age ≥ 50)(increase of 0.4097 visits,  which is just barely significant,  since the SE is 0.39)Interestingly,  individuals with no major health condition at baseline (health_baseline == 0) show a larger and significant increase (increase of 0.645 visits,  which is significant since SE is 0.239) in visits compared to those with a health condition (health_baseline == 1) (increase of 0.418 visits which not significant since SE is 0.468).

```latex
> group_conditions <- list(
+     "female == 0" = "female == 0", 
+     "female == 1" = "female == 1", 
+     "age < 50" = "age < 50", 
+     "age >= 50" = "age >= 50", 
+     "race_white == 0" = "race_white == 0", 
+     "race_white == 1" = "race_white == 1", 
+     "health_baseline == 0" = "health_baseline == 0", 
+     "health_baseline == 1" = "health_baseline == 1"
+ )
> 
> results <- data.frame(Group = character(),  Beta1 = numeric(),  SE = numeric(),  stringsAsFactors = FALSE)
> 
> for (group in names(group_conditions)) {
+     condition <- group_conditions[[group]]
+     model <- lm(as.formula(paste("count_visit_dr ~ treated + numhh_list")),  data = subset(ohie_data,  eval(parse(text=condition))))
+     beta1 <- coef(model)["treated"]
+     se <- su[STATS II PSET III](STATS%20II%20PSET%20III.md)mmary(model)$coefficients["treated",  "Std. Error"]
+     results <- rbind(results,  data.frame(Group = group,  Beta1 = beta1,  SE = se))
+ }
> print(results)
                        Group     Beta1        SE
treated           female == 0 0.3420393 0.2836245
treated1          female == 1 0.7926379 0.3118582
treated2             age < 50 0.6440451 0.2588436
treated3            age >= 50 0.4097361 0.3933661
treated4      race_white == 0 0.1638626 0.3303053
treated5      race_white == 1 0.8066601 0.2760115
treated6 health_baseline == 0 0.6450163 0.2393665
treated7 health_baseline == 1 0.4180334 0.4681090
```

---

1. Returning to the full data and still focusing on the number of doctor office visits,  let’s also try controlling for education.
- Using information in the variables hs degree and college degree,  create a new indicator vari-able if someone DOES NOT have a high-school degree,  call this new variable NO_hs_degree.
- Try running each of the following regressions. Discuss how your estimated treatment effect,  the precision of this estimate (standard error),  and R2 changes from just including numhh list,  i.e. model (1) above. If you cannot estimate a coefficient,  explain why. (3 points)

> [!NOTE]
> Compared to model (1),  the addition of the the control variables of numhh_list,  hs_degree,  and college_degree,  only slightly changes the estimated treatment effect from 0.5745 to 0.5727. This change does not appear to be significant. since the standard error for both models is about 0.2163,  which is much larger than the actual change from adding the control variable. We cannot conclude that the change in estimated treatment effect is therefore significantly different from zero. This is likely because the$R^2$= 0.0096 is very small meaning that the models only explain a small portion of the variance in doctor office visit. the NO_hs_degree variable in Model (4) does not significantly change the treatment effect estimate or its precision compared to Model (3).

For Model (3)$$count_visit\_dr = \beta_0 + \beta_1 treated + \beta_2 numhh\_list + \beta_3 hs\_degree + \beta_4 college\_degree + u$$

- Estimated Treatment Effect ($β_1$): 0.5745
- Standard Error of$β_1$: 0.2163
- R-squared: 0.0096

For Model (4)$$count\_visit\_dr = \beta_0^\prime + \beta_1^\prime treated + \beta_2^\prime numhh\_list + \beta_3^\prime NO\_hs\_degree + \beta_4 hs\_degree + \beta_5 college\_degree + u^\prime$$

- Estimated Treatment Effect ($β_{1}^{'}$): 0.5727
- Standard Error of$β_{1}^{'}$: 0.2164
- R-squared: 0.0096

```latex
> ohie_data$NO_hs_degree <- 1 - ohie_data$hs_degree
> 
> model_3 <- lm(count_visit_dr ~ treated + numhh_list + hs_degree + college_degree,  data = ohie_data)
> summary(model_3)

Call:
lm(formula = count_visit_dr ~ treated + numhh_list + hs_degree + 
    college_degree,  data = ohie_data)

Residuals:
    Min      1Q  Median      3Q     Max 
 -8.014  -5.568  -3.568   0.158 138.432 

Coefficients:
               Estimate Std. Error t value Pr(>|t|)    
(Intercept)      6.9842     0.4178  16.715  < 2e-16 ***
treated          0.5745     0.2163   2.657   0.0079 ** 
numhh_list      -1.9910     0.2509  -7.936 2.28e-15 ***
hs_degree        1.2746     0.2724   4.679 2.92e-06 ***
college_degree   2.4467     0.3978   6.151 7.95e-10 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 11.84 on 12153 degrees of freedom
  (71 observations deleted due to missingness)
Multiple R-squared:  0.009592, 	Adjusted R-squared:  0.009266 
F-statistic: 29.43 on 4 and 12153 DF,   p-value: < 2.2e-16

> model_4 <- lm(count_visit_dr ~ treated + numhh_list + NO_hs_degree + hs_degree + college_degree,  data = ohie_data)
> summary(model_4)

Call:
lm(formula = count_visit_dr ~ treated + numhh_list + NO_hs_degree + 
    hs_degree + college_degree,  data = ohie_data)

Residuals:
    Min      1Q  Median      3Q     Max 
 -8.014  -5.568  -3.568   0.158 138.432 

Coefficients: (1 not defined because of singularities)
               Estimate Std. Error t value Pr(>|t|)    
(Intercept)      8.2588     0.3397  24.309  < 2e-16 ***
treated          0.5745     0.2163   2.657   0.0079 ** 
numhh_list      -1.9910     0.2509  -7.936 2.28e-15 ***
NO_hs_degree    -1.2746     0.2724  -4.679 2.92e-06 ***
hs_degree            NA         NA      NA       NA    
college_degree   2.4467     0.3978   6.151 7.95e-10 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 11.84 on 12153 degrees of freedom
  (71 observations deleted due to missingness)
Multiple R-squared:  0.009592, 	Adjusted R-squared:  0.009266 
F-statistic: 29.43 on 4 and 12153 DF,   p-value: < 2.2e-16
```

---

1. Now,  let’s try including all the baseline characteristics as controls to the regression. Rerun the regression of count visit dr on treated,  and control for:
	 numhh list, female, age, race white, hs degree, college degree, health baseline

	 How does your estimated treatment effect,  the precision of this estimate (standard error),  and R2 change from the model just including numhh list (2 points)

> [!NOTE]
> 1. The treatment effect ($\beta_1$for `treated`) increased to 0.585611 from the original effect when only controlling for `numhh_list`,  which suggests a slightly stronger positive impact of treatment on the number of doctor visits when more controls are included. The standard error is similar,  which we expect,  since the inclusion of more control variables cannot lower the precision. Indeed,  we see a decrease in standard error of the coefficient to 0.213681,  which indicates a slightly higher precision. The R-squared value of 0.03257 is higher in the model with all baseline characteristics,  indicating that this model explains a larger portion of the variance in doctor office visits compared to the model with only numhh_list as a control,  since we add more variables that are potentially related to the outcome are in this model. however,  this increase is only slight,  since the original R-squared was 0.0326.

```latex
> model_all_controls <- lm(count_visit_dr ~ treated + numhh_list + female + age + race_white + hs_degree + college_degree + health_baseline,  data = ohie_data)
> 
> summary(model_all_controls)

Call:
lm(formula = count_visit_dr ~ treated + numhh_list + female + 
    age + race_white + hs_degree + college_degree + health_baseline,  
    data = ohie_data)

Residuals:
    Min      1Q  Median      3Q     Max 
-11.226  -5.147  -3.178   0.368 139.813 

Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)      3.408752   0.597213   5.708 1.17e-08 ***
treated          0.585611   0.213681   2.741  0.00614 ** 
numhh_list      -1.611988   0.249436  -6.463 1.07e-10 ***
female           2.715487   0.214414  12.665  < 2e-16 ***
age              0.009106   0.009785   0.931  0.35211    
race_white       1.233884   0.237740   5.190 2.14e-07 ***
hs_degree        0.919203   0.276283   3.327  0.00088 ***
college_degree   2.000781   0.400539   4.995 5.96e-07 ***
health_baseline  2.319483   0.256797   9.032  < 2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 11.68 on 12116 degrees of freedom
  (104 observations deleted due to missingness)
Multiple R-squared:  0.03257, 	Adjusted R-squared:  0.03193 
F-statistic: 50.99 on 8 and 12116 DF,   p-value: < 2.2e-16
```

---

 1. Do you think we should include all these other baseline characteristics as controls to ensure that the treatment effects are unbiased,  or is it sufficient to just control for numhh list? Explain. (1 point)

> [!NOTE]
> Given that these additional baseline characteristics are likely to influence the number of doctor visits,  including them can provide a more accurate and unbiased estimate of the treatment effect since we can reasonably assume that these characteristics might have an influence on both the treatment and the outcome,  such that if we leave them out,  we would have a biased estimate of the treatment effect since some of the variation in the outcome that is attributed to the treatment will actually have come from these omitted variables.

---

1. Do you think we should include all these other the baseline characteristics as controls to improve the precision of our estimated treatment effects? Explain. (1 point)

> [!NOTE]
> Yes,  including the other baseline characteristics as controls improves the precesion of our estimated treatment effects since the standard error decreases,  which effectively means a narrower confidence interval around the estimated treatment effect. This suggests that adding the other baseline characteristics make the estimation of the treatment effect more reliable by accounting for the other sources of variation in the outcome that are not attributable to the treatment.

---

1. Using the model with the full set of controls estimated in Question 4,  conduct a hypothesis test that the treatment effect on the number of doctor office visits is equal to the effect of having a high school degree.

	 Note: In class on Jan 23,  we discussed two different ways to conduct this test. You can choose either method.

### HYPOTHESES

1. Null Hypothesis (H0): Mathematically,  this can be expressed as$\beta_{\text{treated}} = \beta_{\text{hsdegree}}$
1. Alternative Hypothesis (H1):$\beta_{\text{treated}} \neq \beta_{\text{hsdegree}}$
$$F = \frac{(SSR_{\text{restricted}} - SSR_{\text{full}}) / m}{SSR_{\text{full}} / (n - k)}$$
Where:
- $SSR_{\text{restricted}}$is the sum of squared residuals from the restricted model.
- $SSR_{\text{full}}$is the sum of squared residuals from the full model.
- $m$,  or the # of restrictions,  is 1
- $n$is the # of observations
- $k$is the # of parameters estimated in the full model.

```latex
> model_full <- lm(count_visit_dr ~ treated + numhh_list + female + age + race_white + hs_degree + college_degree + health_baseline,  data = ohie_data)
> model_restricted <- lm(count_visit_dr ~ numhh_list + female + age + race_white + college_degree + health_baseline,  data = ohie_data)
> ssr_full <- sum(model_full$residuals^2)
> ssr_restricted <- sum(model_restricted$residuals^2)
> df_full <- df.residual(model_full)
> df_restricted <- df.residual(model_restricted)
> f_statistic <- ((ssr_restricted - ssr_full) / (df_restricted - df_full)) / (ssr_full / df_full)
> p_value <- pf(f_statistic,  df1 = df_restricted - df_full,  df2 = df_full,  lower.tail = FALSE)
> cat("F-Statistic:",  f_statistic,  "\nP-Value:",  p_value,  "\n")
F-Statistic: 9.386777 
P-Value: 8.443641e-05
```

> [!NOTE]
> The F-statistic of 9.386777 is a measure of the ratio of the variance explained by the model constraint,  ceteris paribus,  to the variance unexplained in the full model. A higher value suggests a larger gap between the full and restricted model. Because the test statistic,  which in this case is$F$,  is significantly larger than$1.96$,  and the$p$value of 8.443641e-05 is significantly smaller than$0.05=\alpha$,  we can conclude that the impact of winning the Medicaid lottery (treatment effect) on increasing the number of doctor office visits is significantly different from the impact of having a high school degree.
> __