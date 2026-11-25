<div align="center">

# The HVP Mind

### An experimental language system connecting experience, memory, and decision.

How does a mind's experience shape its next answer—and how can that process be followed from input to output?

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24514802.svg)](https://doi.org/10.5281/zenodo.24514802)
[![Paper](https://img.shields.io/badge/paper-PDF%20·%20152%20pages-b31b1b)](paper/HVP_Mind.pdf)
[![Book](https://img.shields.io/badge/book-GUHCT%20Full%20Edition%206%20·%20848%20pages-6f42c1)](book/GUHCT_Full_Edition_6.pdf)
[![Paper license: CC BY-NC 4.0](https://img.shields.io/badge/paper%20license-CC%20BY--NC%204.0-lightgrey)](LICENSE)
[![Book license: CC BY 4.0](https://img.shields.io/badge/book%20license-CC%20BY%204.0%20·%20free%20for%20all-brightgreen)](book/LICENSE)
[![Commercial](https://img.shields.io/badge/commercial%20use-by%20permission-orange)](#license-and-commercial-use)
[![Source](https://img.shields.io/badge/source-GUHCT%20%2F%20Marvosa-black)](https://github.com/Ajordon30005/marvosa)

**Anthony Jordon** — framework and underlying theory

</div>

---

## What the paper is about

*The HVP Mind* explores a way to bring learning, memory, and decision together in one language system. It is a computational expression of Anthony Jordon's GUHCT framework: experience leaves structure in a field, and that changing field participates in what the system does next.

The paper's goal is to explain that process from the ground up. It defines the arithmetic and follows a complete conversational turn: how input becomes experience, how the current state helps select a continuation, how using that continuation changes the state, and how the answer and saved state are produced. The intention is to make those connections precise enough to follow and examine, rather than presenting an answer without explaining the process behind it.

The system is experimental. The implementation described in the paper uses fixed-point integer arithmetic and does not use neural weights, attention layers, or backpropagation. The paper is about the architecture and the workings of a turn—not a claim that the model is a mature conversational system.

## How the mind works

**Experience creates paths.** As the system receives text, it creates or reinforces paths that connect a word context to a possible continuation. Each live path also has numerical phase and amplitude coordinates. Together, the live paths contribute to a composite memory field shaped by the system's experience.

**The current state takes part in a decision.** To continue a response, the system looks for live paths that exactly match the end of the current context, starting with the most specific supported context. It uses the path coordinates and the current field to score the eligible continuations, then selects one deterministically.

**A decision changes what comes next.** Using a path reinforces it and changes the field before the next continuation is selected. At the end of a turn, reinforced paths are protected, while other paths weaken and can eventually be removed. Experience therefore affects both which continuations are available and the state in which later choices are made.

The finished answer is delivered from its ordered byte representation. Separately, a compact projection of the resulting field is saved to seed a later session. These are different representations with different jobs: the saved line is not a reconstruction of every live path.

## From arithmetic to an answer

The paper follows a complete conversational turn from an observed live state, showing how experience and the current field participate in each choice. Its worked derivation connects those choices to the finished output and the state saved afterward.

## What is in the paper

[`paper/HVP_Mind.pdf`](paper/HVP_Mind.pdf) is a single, self-contained, 152-page specification and worked execution of the current `MindHVP`:

1. **Integer foundations.** Three explicit fixed-point coordinate scales, finite elementary procedures, bootstrap and α-compatibility.
2. **HCL phase–amplitude operations.** FBits, projections, and the memory COMP that is the field's actual law.
3. **Bytes, braids and the HVP processor.** The generator braid, all nine address coordinates, and a verified byte inverse.
4. **The HVPField as one live state.** Native paths, their waves, and ordered anchored composition.
5. **Experience, depth and decision.** Receiving as the training walk, reinforcement and decay, context coherence, depth adaptation, the cascade and conditioned projection.
6. **A complete turn and its stopping proof.** Finite generation with no imposed length cap, byte delivery, and compact persistence.
7. **The full numerical witness.** Every decoded byte, every generator-cache entry, every RESONANCE certificate, and the complete ordered field-wave ledger, so the derivation can be checked line by line.
8. **Source binding.** SHA-256 fingerprints for every source file the mathematics describes, plus the native implementation listings.

### The theorems

| | Statement |
|---|---|
| **Theorem 1** | Canonical verified HVP round trip: a complete output HVP delivers exactly the finished braid's bytes. |
| **Theorem 2** | Anchored field invariant: the field used for conditioning is the same composition maintained by receiving, reinforcement and the cycle. |
| **Theorem 3** | Finite generation from any finite live field, with no caller-imposed output cap. |
| **Theorem 4** | Exact compact-coordinate persistence: the saved line becomes exactly the seed for the next wake. |
| **Theorem 5** | The witness answer is fixed by the native field. |
| **Theorem 6** | Composition of the native turn contracts: the whole turn (learn, generate, stop, deliver, save) holds together. |

The paper also examines how learned paths, selection, reuse, and selective survival can reduce particular operation counts under stated conditions. These are analyses of the system's work, not claims of a measured speed advantage over other models.

## Source and running the mind

Download the [experienced MindHVP ZIP](mindhvp-experienced-copy.zip) for the source tree, conversation entry point, and compact saved state. The seven source files listed in Section 14 of the paper match the fingerprints of the files in this archive.

```bash
unzip mindhvp-experienced-copy.zip
cd mindhvp
python3 -u hcl-ai/talk.py
```

The included `hcl-ai/mind-hvp.line` matches the seven-integer **post-turn** save in the paper. Running the conversation can update that file, so keep a separate copy if you want to preserve the supplied state. The compact line carries the aggregate state rather than the complete live paths; Section 8.4 explains the distinction.

## Scope, stated plainly

This paper is a **source-exact derivation** of one connected system, not a benchmark claim. "Exact" means the exact integer result of the specified procedure, including its floors, branch order and finite series budgets. It does not mean a finite series equals an irrational function. The worked example makes the operations of one turn inspectable; as the system has different experiences, its state and subsequent behavior can also change.

We welcome scrutiny. If a number in the ledger does not reproduce, open an issue with the section and line.

## Background

The HVP Mind is a computational form of Anthony Jordon's **GUHCT** framework. A harmonic field's configurations differ through phase, excitation and organization. **HCL** supplies the operations on those configurations. **MCL** (Möbius Collapse Logic) supplies the passage from an unresolved configuration to a definite outcome. In this mind, experience produces generator sequences, the processor projects them into phase–amplitude coordinates, memory composes them, and generation selects among the continuations that experience has made available.

## The GUHCT book

This repository also includes the full theory behind the HVP Mind: [`book/GUHCT_Full_Edition_6.pdf`](book/GUHCT_Full_Edition_6.pdf), *GUHCT: Complete Theory of Everything*, Full Edition 6 (Anthony Jordon, 25 May 2026, 848 pages). It covers Möbius Collapse Logic (MCL), LOQ-HCL, the Harmonic Computational Language (HCL), OEPST, THRFM, and Mars Theory with the Gear-LQT correspondence.

The book, this repository and the HVP Mind are natively connected. The paper is the computational form of the book's theory, and the paper cites it directly. For example, the motivation for resonant structure is in Chapter 7, the interaction grammar is in Chapter 13, and the wave update quoted in Section 2 of the paper is the book's Eq. 11.64. The book is included here as context, so you can follow each of those references to its source.

**Note on illustrations:** this edition of the book is included without the illustrations that appear throughout the full book. They were left out to keep the file light to download and transport, since the book serves here as context. The images shown in the book are publicly available, so they are easy to find by searching for them.

**The book is free for everyone.** It is a theory of everything, made for everyone. You may use it for any purpose, including commercial purposes, as long as you credit Anthony Jordon. See [`book/LICENSE`](book/LICENSE) (CC BY 4.0).

## Citation

If you use, discuss or build on this work, please cite it. GitHub's **"Cite this repository"** button reads [`CITATION.cff`](CITATION.cff).

```bibtex
@misc{jordon2026hvpmind,
  title        = {The HVP Mind: An Exact Derivation from Harmonic Arithmetic to a Native Conversational Answer},
  author       = {Jordon, Anthony},
  year         = {2026},
  month        = nov,
  howpublished = {\url{https://github.com/Ajordon30005/apond}},
  doi          = {10.5281/zenodo.24514802},
  note         = {Framework and theory: Anthony Jordon. Document preparation assisted by Manus AI.}
}

@book{jordon2026guhct,
  title        = {GUHCT: Complete Theory of Everything},
  author       = {Jordon, Anthony},
  edition      = {Full Edition 6},
  year         = {2026},
  month        = may,
  howpublished = {\url{https://github.com/Ajordon30005/apond}}
}
```

## License and commercial use

This repository uses two licenses. Both require credit to Anthony Jordon.

**The GUHCT book is free for everything.** It is licensed under **[Creative Commons Attribution 4.0](book/LICENSE)**. Anyone may read, share, adapt and build on it for any purpose, including commercial purposes, without asking. The only requirement is clear credit to **Anthony Jordon** as its author and the originator of GUHCT.

**The HVP Mind paper and documentation** are licensed under **[Creative Commons Attribution-NonCommercial 4.0](LICENSE)**, with these terms:

- **Credit is required.** Any sharing, quotation, adaptation or reimplementation must credit **Anthony Jordon** as the originator of the HVP Mind and its underlying theory.
- **Non-commercial use is free.** That covers research, study, teaching, review and reproduction.
- **Commercial use requires a written agreement.** If you want to use this work in a product, service, commercial R&D or paid offering, let's talk: **xpguhct@gmail.com**

The experienced-copy archive includes its own `mindhvp/LICENSE` (GNU GPL v3); consult the archive for the source terms. The paper and book licenses above remain separate.
