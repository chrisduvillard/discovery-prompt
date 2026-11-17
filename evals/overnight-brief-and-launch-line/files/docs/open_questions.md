# Timings we cannot explain

- Throughput drops about 18% on files whose mean field length is 9 to 12 bytes, against both shorter and longer
  fields. Seen on x86 only.
- Quote-heavy files run relatively faster on an Apple M2 than on the reference machine, against each machine's own
  baseline.
- A cliff at lines longer than 4,096 bytes: throughput falls about 30% and does not recover for the rest of the file.
- Timings on the wide-table file (2,000 columns) are bimodal: about half the runs are 11% slower. Not explained by
  thermal state.
- The field arena (tried #9) helps less the more columns a file has.
- `perf stat` shows branch mispredictions at 0.4% overall but 6% inside `field.rs::finish_row`.
