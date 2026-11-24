<div align="center">

# The HVP Mind

### A conversational AI you can check by hand.

**No neural weights. No attention layers. No backpropagation. No floating point.**<br>
One integer state transition, derived end to end, from the first fixed-point operation to the last byte of the answer.

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

## The result in three lines

Before typing anything into the running system, the paper calculates its answer on paper, with exact integers, from the system's observed live state:

```
you    hauling,
ai     hauling, more lunch.
```

The paper predicts the two continuations (`more`, then `lunch.`), the moment generation stops, all nine output-address parameters, every one of the twenty output bytes, and the seven-integer line the mind saves afterward. The same input was then typed into the **unchanged** native `talk.py` process. Its answer and its saved state matched the calculation **exactly**.

Nothing was edited, injected, or re-run to get there. Every number is in the paper.

## Why this is different

Today's language models are trained black boxes: billions of floating-point weights fitted by gradient descent, inspected after the fact with probes and heatmaps. Explaining *why* one produced a particular word is an open research problem.

The HVP Mind is built the other way around. Every stage has a lower-level arithmetic meaning, and every stage is written down:

| Conventional LLM | HVP Mind |
|---|---|
| Learned embedding matrices | Byte-labelled generator braids with an exact inverse |
| Attention over a context window | One live harmonic field (`HVPField`) composed by phase–amplitude COMP |
| Backpropagation through a dense network | Learning by experience: path creation, self-COMP reinforcement, decay and selective survival |
| Softmax sampling | Deterministic MCL selection over an exact integer score vector |
| `max_new_tokens` cap | A proven native stopping condition |
| Checkpoint of opaque tensors | A compact seven-integer persistence line that re-seeds the next session exactly |

You can trace any selected word back through its score, its live path, its processor spectrum and its generator data, without a hidden classifier anywhere in the chain.

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

The paper also derives where the architecture's efficiency comes from: learned suffix qualification, single-trajectory collapse, in-place reuse, exact cancellation branches and selective survival. It shows algebraically how experience reduces native work.

## Reproduce it

The executable source is the GUHCT / Marvosa repository. From that repository's root:

```bash
git clone https://github.com/Ajordon30005/marvosa
cd marvosa
python3 -u hcl-ai/talk.py
```

The door loads the existing `hcl-ai/mind-hvp.line` (there is no silent fresh start). Type one input, wait for the answer, then type the next. Section 9 of the paper describes correct operation, and Section 14 lists the SHA-256 fingerprints that bind each equation to the exact source it describes.

## Scope, stated plainly

This paper is a **source-exact derivation** of one connected system, not a benchmark claim. "Exact" means the exact integer result of the specified procedure, including its floors, branch order and finite series budgets. It does not mean a finite series equals an irrational function. The worked example is deliberately small so that every intermediate value fits on the page. The claim is not scale. The claim is that a working conversational turn can be fully specified, predicted and verified with nothing left hidden.

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

The Marvosa source code is distributed under its own license in its own repository.
