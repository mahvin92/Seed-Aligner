# Seed Aligner

**Seed Aligner** is a lightweight genetic preprocessing module designed to solve a fundamental issue in comparative genomic analysis:  
not all sequence assemblies in databases start at the same genomic region.  

This variation, where some sequences starting internally, others at the end, or beginning can disrupt alignment and embedding analyses such as those performed by [Covary](https://github.com/mahvin92/Covary).  Seed Aligner addresses this by locating conserved “seed” consensus regions across sequences and normalizing sequence orientations.

---

## 🌱 Overview

Unlike conventional Multiple Sequence Alignment (MSA) tools that align entire sequece, Seed Aligner focuses on identifying a short, conserved seed region and reassembling the sequences around it.

### Key Features
- 🔍 **Seed Region Identification:** Finds a consensus sequence (dafault= 100 nt; start of the reference) shared across all genomes.
- 🔄 **Sequence Reorientation:** Repositions fragments flanking the seed to ensure all sequences start consistently.
- 🧩 **MSA-Free Normalization:** Reduces computational cost by skipping full alignments.
- ☁️ **Colab Compatible:** Runs entirely on Google Colab as a Jupyter Notebook for fast prototyping.

---

## ⚙️ Workflow

1. **Input:** Multi-FASTA file containing complete genomes.
2. **Seed Detection:** Paste the reference sequence or assembly.
3. **Sequence Rearrangement:**  
   - If the genome starts after the seed → shift 5′ fragment to the end.  
   - If the genome starts before the seed → ensure seed alignment consistency.
4. **Output:** Normalized FASTA file suitable for Covary input and other FASTA-associated analyses

---

## 🧩 Example

Reference assembly: [SEED] ... AGTCC ... TTGAC

| Changes | Example (reorientation) |
|------|----------------------|
| Original sequence | `TTGAC... [SEED] ...AGTCC` |
| Normalized output | `[SEED] ...AGTCC...TTGAC` |

The sequence will now start uniformly at the seed region like the reference assembly.

---

## 🚀 Run in Google Colab

You can open the notebook directly in Google Colab:


