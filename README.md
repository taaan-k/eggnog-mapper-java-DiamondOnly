# eggnog-mapper-DiamondOnly (Pure Java)
## English

### Overview

This project is a pure Java implementation designed to reproduce the **DIAMOND-based workflow** of [eggnog-mapper](https://github.com/eggnogdb/eggnog-mapper), with the goal of improving cross-platform usability through Java.

The implemented workflow covers the following chain:

`hits -> seed orthologs -> (optional) annotation -> (optional) orthologs`

### Requirements

Before running this program, make sure the following dependencies are available:

- **Java** must be installed on your computer.
- A working `diamond` executable is required.
  - By default, the program will first try:
    - `eggnogmapper/bin/diamond`
  - If not found, it will try `diamond` from the system `PATH`.
  - You can also explicitly specify the executable path with `--diamond_bin`.
- The same three database files required by the original eggnog-mapper are also required:
  - `eggnog_proteins.dmnd`
  - `eggnog.db`
  - `eggnog.taxa.db`

### Validation

The annotation results of this program were compared with those of the original eggnog-mapper using the same databases.

For 10 test genome protein datasets, the annotated entries were consistent with those produced by the original program.

Tested species:

- *Acanthaster planci*
- *Ananas comosus*
- *Aphanomyces astaci*
- *Arabidopsis thaliana*
- *Armillaria ostoyae*
- *Caenorhabditis elegans*
- Human
- Mouse
- *Oryza sativa*
- *Sus scrofa*

### Usage

```bash
java -jar eggnog_java.jar -m diamond -i <input.fa> --itype proteins|CDS -o <out_prefix>
