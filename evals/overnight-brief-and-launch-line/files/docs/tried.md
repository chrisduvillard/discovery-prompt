# Optimisations tried

| # | What | Source of the idea | Dev corpus | Kept |
| --- | --- | --- | --- | --- |
| 1 | AVX2 delimiter scan, 32 bytes a step | simdjson stage 1 (Langdale and Lemire 2019) | +41% | Yes |
| 2 | `memchr3` for the scalar tail | BurntSushi's memchr | +3% | Yes |
| 3 | Branchless quote state by carry-less multiply | simdjson | +9% | Yes |
| 4 | Structural bitmaps, then a second pass (Mison-style) | Li et al. 2017 | +12% | Yes |
| 5 | Huge pages for the input mapping | folklore | 0% | No |
| 6 | Software prefetch 256 bytes ahead | folklore | -1% | No |
| 7 | Profile-guided optimisation | rustc book | +4% | Yes, release profile |
| 8 | Parallel chunks with speculative quote parity | Ge et al. 2019 (Instant Loading line) | +3.1x on 16 threads, files over 64 MB | Yes |
| 9 | Field arena instead of per-field `Vec` | own | +7% | Yes |
| 10 | Escape lookup table | own | 0% | No |
| 11 | AVX-512 scan | simdjson | -6% on the reference machine, frequency drop | No |
| 12 | Unaligned loads replaced by aligned with a scalar head | folklore | 0% | No |
| 13 | SWAR scan for machines without AVX2 | Mycroft's trick | +22% on the fallback path only | Yes |

What we now believe: the scan is at memory bandwidth on long fields, so what is left is in short fields and in
field materialisation; anything published for JSON has been tried.
