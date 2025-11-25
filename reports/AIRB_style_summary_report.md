📘 Auto Insurance Pricing Fairness Model
Regulatory Evaluation Summary Report (Markdown Edition)

Prepared by: Glenn Barnes
Date: [Insert]

1. Purpose of This Report

This report summarizes an evaluation of a synthetic auto insurance pricing model, following the workflow and communication style used in regulatory environments such as the Alberta Automobile Insurance Rate Board (AIRB). The analysis illustrates how regulators assess:

Model performance

Segment-level fairness

Consumer impact

Pricing appropriateness

All data are synthetic and used solely for demonstration.

2. Dataset Overview

Exploratory analysis of the synthetic policy-year dataset shows:

Driver Demographics

Ages range from 19 to 75

Young drivers (19–25) and older drivers (65+) appear frequently in the dataset

Distribution is reasonably wide for demonstration

Vehicle & Rating Features

Vehicle types: Sedan, SUV, Coupe, Truck, Hatchback

Territories: Urban, Rural

Coverage: Collision, Comprehensive, Third Party

Premium & Loss Patterns

Premiums range from ~$600 to $2,100

Claim costs are heavily right-skewed, with many zero-claim years and several large losses (up to ~$6,200)

Pure premium variability is driven by severity rather than frequency

3. Modeling Approach

Two pricing models were developed to estimate pure premium (loss per exposure):

3.1 GLM-Style Linear Regression (Baseline Model)

Transparent and easily interpretable

Serves as a reference point for fairness and regulatory suitability

Model Output

MAE: 1536.5351  
R²: -1.8120


A negative R² indicates that the model performs worse than predicting the mean, which is expected given the small dataset and high claim volatility.

3.2 Random Forest Regressor (Non-Linear Benchmark)

Captures complex interactions not modeled by the GLM

Useful for exploratory comparison

Model Output

MAE: 1359.1667  
R²: -1.4121


Performance improves relative to GLM but still yields a negative R² due to limited data volume and extreme claim severity.

4. Key Findings from Exploratory Data Analysis

Visual analysis highlights several meaningful trends:

4.1 Driver Age Effects

Drivers <25 show extremely high pure premium volatility

Ages 25–40 exhibit the lowest pure premium values

Ages 65+ show elevated loss severity and variability

U-shaped pattern is consistent with real-world actuarial expectations

4.2 Premium Distribution

Premiums vary logically across vehicle types:

Coupes and Sedans → highest average premiums

Trucks → lowest premiums

SUVs → mid-range

Distribution appears stable and consistent with expected risk profiles

4.3 Claim Frequency & Severity

Claim costs are highly skewed, with most observations at zero

A handful of catastrophic claims dominate pure premium

Comprehensive shows higher frequency in this sample

Third Party shows low frequency but notable large losses

This reflects typical auto insurance loss behaviour.

4.4 Territorial Differences

Average claim severity:

Rural: ~2,100

Urban: ~1,050

Rural severity is roughly double, consistent with:

Larger vehicle types

Longer travel distances

Greater impact speeds in collisions

5. Fairness & Bias Considerations

Although synthetic, the dataset allows for meaningful fairness insights.

5.1 Age-Based Fairness

Younger drivers are priced higher due to volatility → actuarially justified

25–40 group shows lowest costs → no evident unfairness

65+ group experiences higher severity → requires monitoring to ensure no age-related discrimination

5.2 Territorial Fairness

Rural drivers face higher severity

Appropriate from a risk standpoint

Small dataset → insufficient volume for formal credibility

5.3 Coverage Type

Collision and Comprehensive behave as expected

Third Party’s low frequency but high severity is typical

No systemic unfairness identified

6. Model Appropriateness

Given performance metrics:

Both models show weak predictive power due to sample size and loss volatility

GLM remains the most appropriate baseline for fairness evaluation

Random Forest improves accuracy but reduces interpretability

Regulatory Suitability

✔ Suitable for demonstration
✔ Aligned with AIRB analytical workflow
✘ Not suitable for real-world pricing decisions

7. Consumer Impact Commentary

If these patterns were real:

Young drivers would face higher premiums, raising affordability concerns

Rural drivers may be disproportionately impacted by higher severity

Older drivers may experience higher premiums → fairness review recommended

Model instability suggests insurers would require more credible data

8. Recommendations

Increase data volume for stability (multi-year, multi-policy).

Consider GLM enhancements: interaction terms, Tweedie distributions.

Apply credibility adjustments to high-volatility segments.

Expand segmentation (vehicle symbol, driver experience, finer territory levels).

Perform residual analysis to detect systematic under/over-pricing.

Provide plain-language consumer summaries if used for filings.

9. Conclusion

This synthetic demonstration mirrors several core elements of AIRB regulatory evaluation:

Understanding model structure

Assessing appropriateness and fairness

Reviewing demographic and territorial impacts

Interpreting pricing results in a consumer-protection context

Despite limitations due to sample size, the project showcases the methodology, thinking, and analytical ability required for regulatory data science and actuarial oversight.
