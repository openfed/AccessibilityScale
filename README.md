# AccessibilityScale
A proposal for a more formal Accessibility Scale metric based on the EN 301 549 v3.2.1 standard

# **Why?**

- Only three conformity levels in the WAD
    - Full
    - Partial
    - Non
- Small errors immediately lead to “partial conformance”
- Heavy investment in accessibility will not necessarily be reflected in a change in conformance level

# **Goals**

- Increase the granularity – more opportunities for noticeable improvement
- Better vision on the impact of accessibility issues for different use cases
- Less legalistic and more public-friendly communication
- Clear and objective approach

# **Sources**

- Based on EN 301 549 v3.2.1
    - Criteria (list Annex A Table A.1)
    - “Functional performance statement” (Annex B Table B.1) – renamed to “Use Cases” here
    - Weighing based on Table B.2 “Primary” and “Secondary” relationships of criteria vs Use Cases
- Based on the presence of an Accessibility Statement
- Evaluations based on in-depth or simplified audits
- Inspired by the Dutch “Accessibility status” logic and presentation on  
<https://www.digitoegankelijk.nl/toegankelijkheidsverklaring/status>

# **In-Depth audit scoring**

-  Across 10 use cases, calculate a %-based score based on pass/fail – “Not Applicable” criteria not included
    -  Weighed calculation (prototype!!!) per use case
        - Primary relationship: 1
        - Secondary relationship: 0.5
        - No relationship: 0
    - (Weighted sum of all “pass” criteria) / (Weighted Sum of all applicable criteria)
- Final score is
    - Average of score per use case
    - *Except* if at least one use case scores below a threshold (25%) – then total score = lowest score

# **Simplified audit “scoring”**

- Three levels
    - 0 errors detected in simplified audit
    - \>=50% of verified criteria failed
    - <50% of verified criteria failed
- Important distinction with in-depth
    - Simplified audit based on automated checks can establish violations (“fail”)
    - Cannot (for most criteria) establish “pass” since automated testing will miss certain failure cases
    - So the “%” here is something very different from the in-depth scoring

# **Visualisation of the scale**

- Using letters to indicate conformance level (A+, A,…,F)
- Visuals inspired on Nutriscore
<img src="https://raw.githubusercontent.com/openfed/AccessibilityScale/refs/heads/main/svg/scale-horizontal-b.svg" height="100">

# Conformance levels

- Level A+: score 100% (in depth audit) and valid accessibility statement
- Level A: score >98% (in depth audit) and valid accessibility statement
- Level B: score >=60% (in depth audit) and valid accessibility statement
- Level C: either
    - score <60% (in depth audit) and valid accessibility statement
    - no failures on simplified audit and valid accessibility statement
- Level D: =<50% failures on simplified audit and valid accessibility statement
- Level E: either
    - \>50% failures on simplified audit and a valid accessibility statement
    - no audit but a valid accessibility statement
- Level F: No valid accessibility statement

# **Visualisation on in-depth audit report**

Screenshot of detailed explanation of the conformity level (in Dutch)

- States the validity/presence of an accessibility statement
- Provides the aggregate score
- Shows a vertical visualisation of the scale, in this example “C”, and a sentence stating “the score for this website is lower than 60%”
- For each use case
    - shows a visual and textual representation of the indiviual scores
    - where a score is below the 25% threshold, the visual is in a different colour and surrounded by a thick outline of the same colour

# **Some remarks**

- We did excluded the Use Case “4.2.11 Privacy” because it is linked to a very small set of criteria and would have a disproportionate effect on the score
- We did include Use Case “4.2.9 Minimize Photosensitive Triggers” because violating it has such an immediate and high impact on the affected user
- Note that all proposed thresholds and weights described need to be tested against more real-world examples before finalisation
