# Perplexity Prompt Guide

A practical guide to writing effective Perplexity prompts, illustrated with a real research conversation.

---

## Core Prompt Principles

### 1. Ask a Specific, Answerable Question
State the exact molecule, model, condition, or comparison you care about. Perplexity pulls from primary literature, so narrow questions yield more precise source retrieval.

**Weak:** "Tell me about liver cancer genes"
**Strong:** "Is cyclin E1 or cyclin E2 thought to be the driver of HCC in mice?"

### 2. Interrogate the Answer — Follow Up with Challenges
After the initial answer, ask whether any papers contest the claim. This surfaces nuance and prevents you from anchoring on the consensus view without knowing its limits.

**Prompt pattern:**
> "Are there any papers that challenge this idea?"

### 3. Request Structured Exports
Once you have the sources you need, ask Perplexity to export them in a machine-readable format. This saves manual copy-paste and is useful for building citation libraries.

**Prompt pattern:**
> "Can you export all of the links and citations to a CSV?"

### 4. Anchor Ambiguous Terms
If your question could refer to multiple gene families (e.g., "cyclin 1 or 2"), acknowledge the ambiguity and ask Perplexity to address both interpretations.

---

## Example: HCC Cyclin Driver Research

### Thread title
**"Is cyclin 1 or 2 thought to be the driver of HCC in mice"**

---

### Turn 1 — Initial question

**Prompt:**
> Is cyclin 1 or 2 thought to be the driver of HCC in mice?

**Perplexity answer summary:**

Cyclin E1 (Ccne1), often together with its partner Cdk2, is the best-supported E-type cyclin driver of hepatocellular carcinoma (HCC) initiation and progression in mouse models, whereas Cyclin E2 (Ccne2) plays more of a compensatory or later-stage role.

**Evidence in mice:**
- Mice lacking Ccne1 show markedly reduced DEN-induced HCC initiation, while Ccne2-knockout mice still develop HCC if Ccne1 is present — implying Ccne1 is the critical "driver" in early hepatocarcinogenesis.
- In chronic injury models (e.g., NEMOΔhepa), loss of Ccne1, but not Ccne2, attenuates hepatitis and liver tumor formation, pointing to Ccne1 as the dominant oncogenic cyclin E in liver.
- Mechanistic work shows that Ccne1 can drive HCC progression partly via kinase-independent functions (beyond Cdk2), strengthening its role as an oncogenic driver rather than just a generic cell-cycle component.

**Disambiguation note from Perplexity:**
> "If by 'cyclin 1 or 2' you meant the E-type cyclins, the consensus from these murine studies is that Cyclin E1 is the primary driver of HCC, with Cyclin E2 unable to fully substitute when Ccne1 is absent. If you meant a different cyclin family (e.g., D1 vs D2), data also strongly support Cyclin D1 (Ccnd1) as an HCC driver in mouse transgenic models, but that is a separate axis from the E-type cyclins."

---

### Turn 2 — Challenge the consensus

**Prompt:**
> Are there any papers that challenge this idea?

**Perplexity answer summary:**

There are not (yet) strong mouse in vivo data that "flip" the conclusion that cyclin E1 is the main E-type cyclin driver of HCC initiation, but several papers complicate or soften that simple hierarchy.

**Papers that nuance or complicate the E1-as-driver model:**
- A PNAS study using conditional double-knockout mice showed that **global ablation of both E-type cyclins (E1 and E2) is required to halt liver cancer progression**; loss of Ccne1 alone mainly impairs initiation, while advanced tumors can be maintained by either E1 or E2 via kinase-independent functions.
- In NEMOΔhepa models, hepatocyte-specific Ccne1 deletion attenuates hepatitis and HCC, but **CDK2 deletion does not**, and late tumors show increased CDK1 rather than CDK2 activity — challenging the idea that E1 drives HCC mainly through canonical Cdk2-dependent kinase activity.

**Data elevating roles for non-E1 cyclins:**
- A study reports that **CCNE2 expression can be upregulated by METTL3** and promotes HCC cell growth, invasion, stemness, and radioresistance in vitro — arguing that E2 can behave as a bona fide oncogenic driver in some HCC contexts.
- A Nature Communications study classifying human HCCs finds a subclass defined by **Cyclin A2/E1 activation** as particularly aggressive, suggesting the most malignant biology is tied to a broader S-phase cyclin program rather than E1 alone.

**Take-home:**
> "In carcinogen and chronic-injury mouse models, the genetic evidence still points to Ccne1 being uniquely essential for initiation, with Ccne2 unable to fully substitute at that early stage. However, work on double E-cyclin knockouts, Cdk2 independence, and CCNE2-driven phenotypes in HCC cells challenges an overly rigid view that 'E1 is the only driver', and instead supports a model where E1 is dominant for initiation but E1 and E2 together are necessary and partly interchangeable for progression and maintenance of established tumors."

---

### Turn 3 — Export citations

**Prompt:**
> Can you export all of the links and citations to a CSV?

**Result — hcc_cyclin_links_and_citations.csv:**

| label | url | citation_id |
|---|---|---|
| Cyclin E1 in Murine and Human Liver Cancer - PNAS/PMC | https://pmc.ncbi.nlm.nih.gov/articles/PMC8616292/ | web:3 |
| Cyclin E1 & CDK2 initiation, not maintenance | https://www.pnas.org/doi/10.1073/pnas.1807155115 | web:14 |
| Loss of Cyclin E1 attenuates hepatitis and hepatocarcinogenesis | https://pmc.ncbi.nlm.nih.gov/articles/PMC6388396/ | web:7 |
| Kinase-independent function of E-type cyclins in liver cancer | https://www.pnas.org/doi/10.1073/pnas.1711477115 | web:9/web:13 |
| Cyclin E1 and CDK2 critical for initiation (PMC version) | https://pmc.ncbi.nlm.nih.gov/articles/PMC6140539/ | web:2 |
| Role of Cyclin D1 as a mediator of c-Met and β-catenin HCC | https://pmc.ncbi.nlm.nih.gov/articles/PMC2628201/ | web:4 |
| Role of Cyclin D1 as a mediator of c-Met and β-catenin HCC (Cancer Res) | https://aacrjournals.org/cancerres/article/69/1/253/549530/ | web:5 |
| Hepatocellular carcinoma results from chronic cyclin D1 overexpression | https://pubmed.ncbi.nlm.nih.gov/11454681/ | web:10 |
| Expression of Cyclin E1 in hepatic stellate cells | https://pmc.ncbi.nlm.nih.gov/articles/PMC10449804/ | web:12 |
| Expression of Cyclin E1 in hepatic stellate cells (Nature Cell Death & Disease) | https://www.nature.com/articles/s41419-023-06077-4 | web:1 |
| METTL3-activated CCNE2 promotes HCC cell progression | https://www.sciencedirect.com/science/article/pii/S1874471025000210 | web:17 |
| Cyclin A2/E1 activation defines an HCC subclass | https://www.nature.com/articles/s41467-018-07552-9 | web:16 |
| Mouse models of hepatocarcinogenesis review | https://www.oncotarget.com/article/170/text/ | web:11 |

---

## Prompt Templates

Use these as starting points for your own Perplexity research sessions.

```
# Initial query
Is [gene/protein A] or [gene/protein B] thought to be the driver of [disease] in [model/species]?

# Challenge prompt
Are there any papers that challenge this idea?

# Clarify model specificity
Which of these findings hold specifically in [DEN / NEMOΔhepa / fibrosis-driven / etc.] models?

# Export prompt
Can you export all of the links and citations to a CSV?

# Disambiguation prompt
I may be conflating two things — can you address both [interpretation A] and [interpretation B]?
```
