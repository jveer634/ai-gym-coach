# Biomarker & Metabolic Reference Guide

Read this when an uploaded blood report, lab panel, or metabolic test is provided or discussed.

---

## 1. Prime Directive: Non-Diagnostic Communication

You are a **gym coach**, not a medical doctor.
- **Never diagnose diseases or clinical syndromes** (e.g., do not say "You have hypogonadism," "You have anemia," or "You have kidney disease").
- **Describe observed values relative to reference ranges neutrally**: e.g., *"Your serum ferritin is 18 ng/mL, which sits below the lab's lower threshold of 30 ng/mL. In athletes, low ferritin can correlate with unexplained fatigue and reduced aerobic work capacity."*
- **Flag clinically concerning markers** and advise the user to consult their primary care physician or sports medicine specialist.
- **Athletic Context Awareness**: Many blood markers deviate in resistance-trained athletes due to training volume, muscle mass, or sports nutrition (e.g., AST/ALT, Creatinine, Creatine Kinase). Always interpret markers through this lens before alarming the user.

---

## 2. Key Biomarker Panels for Lifters & Athletes

### A. Hormonal & Endocrine Health
| Marker | Athletic & Training Relevance | Nutritional / Lifestyle Modulation |
| :--- | :--- | :--- |
| **Total Testosterone** | Regulates muscle protein synthesis, recovery, and energy. Low values often mirror extreme caloric deficits, overreaching, or severe sleep disruption. | Adequate dietary fats ($0.6-1.0\text{ g/kg}$), micronutrient sufficiency (Zinc, Vitamin D3), and recovery management. |
| **Free Testosterone** | The bioavailable fraction not bound to SHBG or albumin; reflects actual androgenic tissue stimulation. | Lowering excessive lifestyle stress, resolving chronic caloric deficits. |
| **SHBG (Sex Hormone-Binding Globulin)** | Elevated in prolonged ketogenic diets, deep deficits, or overtraining; low in insulin resistance. | Carbohydrate refeeds, caloric surplus/maintenance. |
| **Estradiol ($E_2$)** | Essential for male and female joint health, bone mineral density, lipid profiles, and neuroprotection. | Balance body fat levels; avoid suppressing fats below threshold. |
| **Cortisol (Morning Serum)** | Catabolic glucocorticoid. Chronically elevated morning levels indicate systemic fatigue or poor recovery; flat diurnal slopes signal burnout. | Sleep hygiene, carbohydrate timing post-workout, stress mitigation. |

### B. Thyroid & Metabolic Health (Adaptive Thermogenesis)
| Marker | Athletic Relevance | Coaching / Caloric Interpretation |
| :--- | :--- | :--- |
| **TSH (Thyroid Stimulating Hormone)** | Primary screening marker for thyroid gland output. | Elevated TSH with low $T_3$ may reflect thyroid fatigue from chronic dieting. |
| **Free $T_3$ (Triiodothyronine)** | The active metabolic driver. Drops quickly during aggressive hypocaloric phases (adaptive thermogenesis). | Trigger for a structured **refeed** or **diet break** (see `recommendation-guidelines.md`). |
| **Fasting Blood Glucose & HbA1c** | Reflects glycation, insulin sensitivity, and glucose handling efficiency. | Dictates carbohydrate distribution and meal timing around workout windows. |

### C. Liver, Muscle Damage & Renal Function (Athletic Nuances)
> [!IMPORTANT]
> **Resistance Training Artifacts**: Heavy eccentric lifting naturally damages muscle fibers, which releases intra-cellular enzymes into circulation. Do not jump to hepatic or renal pathologies without asking about recent intense workouts!

* **AST (Aspartate Aminotransferase) & ALT (Alanine Aminotransferase)**:
  - Both enzymes are found in skeletal muscle as well as liver tissue. AST/ALT can remain elevated for 48–96 hours after heavy resistance training.
  - *Coaching Cue*: Inquire if the blood was drawn within 48 hours of an intense leg or back session. Recommend resting 72 hours before re-testing if liver markers are flagged in isolation.
* **Creatine Kinase (CK)**:
  - Direct proxy for skeletal muscle micro-trauma. Extreme elevations ($>10,000\text{ U/L}$) accompanied by dark tea-colored urine indicate possible rhabdomyolysis—refer immediately to emergency care.
* **Serum Creatinine & eGFR (Estimated Glomerular Filtration Rate)**:
  - Creatinine is a breakdown product of creatine phosphate in skeletal muscle.
  - Highly muscular individuals and those supplementing with **Creatine Monohydrate** often exhibit elevated serum creatinine and artificially suppressed eGFR without any underlying renal dysfunction.
  - *Coaching Recommendation*: Suggest asking their physician for a **Cystatin C** test, which measures kidney filtration independent of muscle mass or dietary creatine.

### D. Hematology, Iron Status & Oxygen Delivery
| Marker | Athletic Threshold & Relevance | Actionable Steps |
| :--- | :--- | :--- |
| **Ferritin** | Iron storage protein. Crucial for mitochondrial ATP generation and aerobic threshold. Optimal athletic target is typically $>40-50\text{ ng/mL}$. | High-bioavailability dietary iron (heme iron from lean beef/poultry, or plant iron paired with Vitamin C). Refer to physician if severe deficiency. |
| **Hemoglobin & Hematocrit** | Oxygen carrying capacity of red blood cells. Low values compromise muscular endurance and time to exhaustion. | Check iron panel, B12, folate, and hydration status. |
| **RBC (Red Blood Cell Count)** | Baseline oxygen delivery. Highly sensitive to altitude, endurance conditioning, and micronutrient status. | Screen for dietary restrictions (e.g., strict plant-based diets missing $B_{12}$/Iron). |

### E. Micronutrients & Bone Mineral Density
* **25-Hydroxy Vitamin D3**:
  - Foundational steroid hormone precursor regulating muscle contractility, testosterone synthesis, and immune defense.
  - *Target*: Optimal athletic range is $40-70\text{ ng/mL}$ ($100-175\text{ nmol/L}$).
  - *Guidance*: If verified $<30\text{ ng/mL}$, recommend baseline supplementation ($2,000-5,000\text{ IU/day}$ of $D_3$ paired with Vitamin $K_2$) and sunlight exposure.
* **Vitamin $B_{12}$ & Folate**:
  - Essential for DNA synthesis, neurological function, and RBC maturation. Common deficiency vector in vegans/vegetarians.
* **Serum Magnesium & Zinc**:
  - Depleted through heavy perspiration. Critical for enzyme catalysis, protein synthesis, and neuromuscular recovery.

### F. Cardiovascular & Systemic Inflammation
* **Lipid Panel (Total Cholesterol, HDL-C, LDL-C, Triglycerides, ApoB)**:
  - Guides saturated vs. unsaturated dietary fat ratios. High triglycerides often correlate with excess refined carbohydrates or caloric surplus.
* **hs-CRP (High-Sensitivity C-Reactive Protein)**:
  - General biomarker of systemic vascular and tissue inflammation. Chronically elevated hs-CRP ($>3.0\text{ mg/L}$) warrants physician evaluation and recovery audit.

---

## 3. Compact Extraction Template (For `session.md`)

When a blood report is provided, extract values into this compact markdown table format. Once created, never re-parse the raw report file.

```markdown
### Extracted Biomarker Audit
| Biomarker | Result | Reference Range | Status | Coaching / Training Relevance |
| :--- | :--- | :--- | :--- | :--- |
| 25-OH Vitamin D | 21.4 ng/mL | 30.0 - 100.0 ng/mL | Low | Sub-optimal; impact on bone/immune recovery. |
| Serum Ferritin | 28 ng/mL | 30 - 400 ng/mL | Low | Sub-optimal iron stores; correlates with endurance fatigue. |
| Creatinine | 1.35 mg/dL | 0.70 - 1.30 mg/dL | Borderline High | Common artifact of 5g/day creatine intake & high lean mass. |
| Total Testosterone| 580 ng/dL | 250 - 900 ng/dL | In Range | Healthy baseline for hypertrophy phase. |
```

---

## 4. Multi-Report Trend Tracking (For `progress-log.md`)

When a user provides subsequent blood reports over months of coaching, log delta changes to verify whether dietary interventions resolved prior deficiencies:

```markdown
- **Biomarker Delta (2026-04-10 vs 2026-08-20)**:
  - Vitamin D: 21.4 ng/mL → 48.2 ng/mL (Resolved via 4,000 IU D3+K2)
  - Ferritin: 28 ng/mL → 55 ng/mL (Resolved via increased dietary iron & vitamin C)
  - Fasting Glucose: 92 mg/dL → 86 mg/dL (Improved insulin sensitivity)
```
