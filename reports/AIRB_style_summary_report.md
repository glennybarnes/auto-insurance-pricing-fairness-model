
# Auto Insurance Pricing Fairness Model  
**Regulatory Evaluation Summary Report**  

*All data are synthetic for demonstration purposes.*  

---

## 2. Dataset Overview  
- **Driver Demographics:** Ages 19–75; young (19–25) and older (65+) frequent  
- **Vehicle & Rating Features:** Sedan, SUV, Coupe, Truck, Hatchback; Urban/Rural; Collision, Comprehensive, Third Party  
- **Premium & Loss Patterns:** Premiums \$600–\$2,100; claims skewed with large losses (~\$6,200); severity drives variability  

---

## 3. Modeling Approach  
Two models estimate pure premium (loss per exposure):  

### GLM-Style Linear Regression (Baseline)  
- Transparent, interpretable  
- **MAE:** 1,536.54  
- **R²:** -1.8120 (worse than mean prediction; expected due to volatility)  

### Random Forest Regressor (Benchmark)  
- Captures complex interactions  
- **MAE:** 1,359.17  
- **R²:** -1.4121 (better than GLM but still negative)  

---

## 4. Key EDA Findings  
- **Age Effects:** U-shaped pattern; <25 high volatility; 25–40 lowest; 65+ elevated severity  
- **Premium Distribution:** Coupes/Sedans highest; Trucks lowest; SUVs mid-range  
- **Claim Patterns:** Highly skewed; catastrophic claims dominate; Comprehensive higher frequency; Third Party low frequency but high severity  
- **Territory:** Rural severity ≈ \$2,100 (double Urban) due to larger vehicles, longer travel, higher impact speeds  

---

## 5. Fairness & Bias  
- **Age:** Young priced higher (justified); 65+ monitor for discrimination  
- **Territory:** Rural higher severity (risk-based, low credibility)  
- **Coverage:** Behaves as expected; no systemic unfairness  

---

## 6. Model Appropriateness  
- Both models weak due to small sample & volatility  
- GLM preferred for fairness review; Random Forest improves accuracy but less interpretable  

**Regulatory Suitability:**  
Demonstration only  
AIRB-aligned workflow  
Not for real-world pricing  

---

## 7. Consumer Impact  
If real:  
- Young drivers → affordability concerns  
- Rural drivers → higher severity impact  
- Older drivers → fairness review needed  
- Model instability → insurers need credible data  

---

## 8. Recommendations  
- Increase data volume (multi-year, multi-policy)  
- Enhance GLM (interactions, Tweedie)  
- Apply credibility adjustments  
- Expand segmentation (vehicle symbol, experience, territory)  
- Perform residual analysis  
- Provide plain-language consumer summaries  

---

## 9. Conclusion  
This synthetic exercise mirrors AIRB evaluation principles:  
- Understand model structure  
- Assess fairness & appropriateness  
- Review demographic & territorial impacts  
- Interpret pricing in consumer-protection context  

Despite limitations, it demonstrates regulatory analytics and actuarial oversight methodology.  
*Prepared by: Glenn Barnes*  
*Date: Nov 25, 25*  

---

## 1. Purpose  
This report evaluates a synthetic auto insurance pricing model using a regulatory-style workflow (e.g., AIRB). Focus areas:  

- Model performance  
- Segment-level fairness  
- Consumer impact  
