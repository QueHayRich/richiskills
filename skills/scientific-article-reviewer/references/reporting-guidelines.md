# Reporting Guidelines Reference

Use this file when Phase 2 identifies a study type that matches a specific guideline. Apply the relevant checklist items during the methodology evaluation in Phase 3.3.

---

## PRISMA — Preferred Reporting Items for Systematic Reviews and Meta-Analyses
*For: Systematic reviews, meta-analyses*

Key checklist items to verify:
1. **Title**: Identified as systematic review/meta-analysis
2. **Abstract**: Structured abstract with background, objectives, data sources, eligibility criteria, participants, interventions, assessment, synthesis methods, results, limitations, conclusions, funding, registration
3. **Introduction**: Rationale clearly stated; explicit research question
4. **Methods**:
   - Protocol registered and accessible (PROSPERO or similar)?
   - Eligibility criteria (PICO: Population, Intervention, Comparison, Outcome)
   - Information sources (databases searched, date range)
   - Search strategy reproducible (full search string provided)?
   - Study selection process described (screening stages, number of reviewers)
   - Data extraction process described
   - Risk of bias assessment (tool used: Cochrane RoB, GRADE, etc.)
   - Summary measures defined (OR, RR, MD, etc.)
   - Synthesis method justified (fixed vs. random effects; why?)
   - Heterogeneity assessed (I², Cochran's Q)?
   - Publication bias assessed (funnel plot, Egger's test)?
5. **Results**: PRISMA flow diagram present? Numbers at each stage?
6. **Discussion**: Limitations of evidence base discussed, not just study limitations

---

## CONSORT — Consolidated Standards of Reporting Trials
*For: Randomized controlled trials (RCTs)*

Key checklist items:
1. **Title/Abstract**: Identified as RCT
2. **Background**: Scientific rationale and explanation of rationale
3. **Methods**:
   - Trial design (parallel, crossover, factorial) and allocation ratio
   - Eligibility criteria for participants
   - Settings and locations
   - Interventions described in sufficient detail for replication
   - Outcomes: pre-specified primary and secondary outcomes; any changes from protocol
   - Sample size: how determined, with assumptions stated
   - **Randomization**: sequence generation method, allocation concealment mechanism, implementation
   - **Blinding**: who was blinded, how, similarity of interventions
   - Statistical methods, including subgroup analyses
4. **Results**:
   - Participant flow (CONSORT flow diagram)
   - Recruitment dates and follow-up
   - Baseline characteristics (Table 1)
   - Numbers analyzed; per-protocol vs intention-to-treat
   - Outcomes and estimation for each primary/secondary outcome
   - Harms and adverse events
5. **Discussion**: Limitations including sources of bias

---

## STROBE — Strengthening the Reporting of Observational Studies in Epidemiology
*For: Cohort, case-control, and cross-sectional studies*

Key items:
1. Study design clearly stated in title or abstract
2. **Methods**:
   - Study design defined and justified
   - Setting (location, relevant dates, follow-up period)
   - Participants: eligibility criteria, selection method, matching criteria if applicable
   - Variables: clearly defined outcomes, exposures, confounders, effect modifiers
   - Measurement: how exposures and outcomes were assessed; blinding if relevant
   - Bias: addressed potential sources of bias
   - Study size: how arrived at
   - Statistical methods including how confounders handled; sensitivity analyses
3. **Results**: Descriptive statistics; unadjusted and adjusted estimates with confidence intervals
4. **Discussion**: Generalizability; sources of potential bias discussed

---

## ARRIVE — Animal Research: Reporting of In Vivo Experiments (v2.0)
*For: Studies using animal models*

Essential items (must be reported):
1. Study design: experimental groups, outcome measures, statistical hypothesis
2. Sample size: number per group and how determined; exclusion criteria
3. Inclusion/exclusion criteria: defined before data collection
4. Randomization: how animals allocated to groups
5. Blinding: who was blinded during outcome assessment
6. Outcome measures: primary and secondary, predefined
7. Statistical methods: tests used, software, alpha threshold
8. Experimental animals: species, strain, age, sex, weight range, source, health status
9. Animal housing: housing conditions, enrichment, diet, water, light cycle
10. Procedures: detailed enough for replication
11. Results: all outcomes including negative results; adverse events

---

## Computational Chemistry / Molecular Modeling Standards
*For: DFT, MD, Monte Carlo, docking, QM/MM, and related computational studies*

These are not a formal checklist but represent the community standard for reproducibility:

### Software and methods
- Software name, version, and citation
- Level of theory / method (DFT functional, basis set, dispersion correction; force field name and version; water model for MD)
- Justification for chosen method (why this functional/force field?)
- Convergence criteria (energy, force, geometry)
- Solvent model if applicable (implicit: PCM, SMD; explicit: box size, periodic boundary conditions)

### Computational setup
- Starting geometries: source (X-ray, homology model, etc.), PDB ID if applicable
- System preparation: protonation states, missing residues, caps, counterions
- Energy minimization and equilibration protocol
- Simulation parameters: timestep, cutoffs, ensemble (NVT/NPT), thermostat/barostat
- Simulation length and number of replicates

### Analysis and validation
- Which trajectory frames analyzed (equilibration discarded?)
- Statistical uncertainties reported (block averaging, standard error of the mean)
- Validation against experimental data (if available)
- Sensitivity analysis for key parameters

### Data availability
- Are input files, parameter files, or trajectories deposited in a repository (Zenodo, Figshare, GitHub)?
- Are scripts for analysis available?

---

## General Scientific Rigor Criteria
*For: Review articles, theoretical/mathematical papers, or studies with no specific guideline*

Apply these baseline standards to any paper:

1. **Reproducibility**: Could an independent researcher reproduce the core findings with the information provided?
2. **Internal consistency**: Are the methods consistent with the stated objectives? Do the conclusions follow from the results?
3. **Transparency**: Are limitations and uncertainties honestly acknowledged?
4. **Appropriate statistics**: Are statistical methods justified and correctly interpreted?
5. **Literature coverage**: Is the cited literature representative and current? Are key contrasting findings acknowledged?
6. **Ethical compliance**: Is ethics approval mentioned where required (human/animal subjects, data privacy)?
