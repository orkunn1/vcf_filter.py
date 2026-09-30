# vcf_filter.py
# vcf-variant-filter

A stream-based Python utility for filtering VCF (Variant Call Format) files based on Quality (QUAL), Read Depth (DP), and PASS status. Supports both plain `.vcf` and gzipped `.vcf.gz` input files.

## Features
- Zero heavy dependencies (uses standard library only)
- Supports compressed `.vcf.gz` files seamlessly
- Filters by minimum QUAL score and read depth (`DP` tag in INFO)
- Breakdown output for SNPs, Insertions, and Deletions

## Quick Start

```bash
# Basic usage with default thresholds (QUAL >= 30, DP >= 10)
python vcf_filter.py sample.vcf.gz -o filtered_output.vcf

# Strict filtering keeping PASS variants only
python vcf_filter.py input.vcf -o clean.vcf --min-qual 50 --min-dp 20 --pass-only