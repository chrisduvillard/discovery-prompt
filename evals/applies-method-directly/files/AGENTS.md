# Rules for agents

- Work on branches named `exp/<short-name>`. Never commit to `main`, never merge, never push.
- **The release corpus is held out.** `bench/release_corpus/` is used only for the numbers in release notes, and
  only Joss runs it. Do not read it, benchmark on it, or list its files. Use `bench/dev_corpus/`.
- **What counts as a speedup.** At least 3% on the median of 20 runs of `cargo bench --bench dev` against the
  branch point, with the two runs' interquartile ranges not overlapping, measured with nothing else running, and
  all 1,912 conformance tests passing. State the expected gain and why before benchmarking.
- No new dependencies and no network installs without asking Joss. No new `unsafe` outside `scan.rs` and
  `quote.rs` without a comment that says why it is sound.
- Record every attempt in `docs/tried.md`, kept or not, with its numbers.
- If something needs Joss (a dependency, a release-corpus run, a change of API), write it in `docs/ASK_JOSS.md`
  and go on with other work.
