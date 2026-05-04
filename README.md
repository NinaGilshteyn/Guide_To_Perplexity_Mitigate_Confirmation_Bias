# Perplexity Research Prompt Guide

A document for writing effective Perplexity.ai prompts for scientific literature research, illustrated with a real multi-turn conversation about cyclin drivers in mouse HCC models.

A guide has now been posted: https://ninagilshteyn.github.io/Guide_To_Perplexity_Mitigate_Confirmation_Bias/

---

## Files

| File | Description |
|---|---|
| `perplexity_prompt_guide.md` | Full prompt guide with principles, a worked example, and reusable templates |

---

## What this covers

**`perplexity_prompt_guide.md`** walks through a complete Perplexity research session in three turns:

1. **Initial specific question** — asking which E-type cyclin (E1 or E2) drives hepatocellular carcinoma (HCC) in mouse models
2. **Challenge follow-up** — asking for papers that contradict or complicate the consensus
3. **Citation export** — asking Perplexity to output all sources as a CSV table (13 papers from PNAS, PMC, Nature, ScienceDirect)

The guide distills these into four prompt principles and a set of copy-paste prompt templates.

---

## Key prompt patterns

```
Is [gene A] or [gene B] thought to be the driver of [disease] in [model]?
Are there any papers that challenge this idea?
Can you export all of the links and citations to a CSV?
```

---

## Example topic

The worked example covers **cyclin E1 vs. cyclin E2 as drivers of HCC in mice**, including:

- DEN-induced and NEMOΔhepa carcinogenesis models
- Ccne1/Ccne2 single and double knockout findings
- CDK2-independent oncogenic functions of E-type cyclins
- METTL3-CCNE2 axis in HCC cell lines
- Cyclin A2/E1 subclass in human HCC classification

---

## Usage

Open `perplexity_prompt_guide.md` before a new Perplexity session to remind yourself of the prompt structure, then adapt the templates at the bottom for your own gene, disease, or model of interest.
