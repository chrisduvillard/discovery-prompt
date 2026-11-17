# Benchmarks

- `cargo bench --bench dev` runs the dev corpus (`bench/dev_corpus/`, 14 files, 6.2 GB): mixed widths, quoted and
  unquoted, short and long fields. About 4 minutes a run.
- `cargo bench --bench release` runs `bench/release_corpus/`. Joss only. See AGENTS.md.
- `cargo test --test conformance` runs the 1,912 conformance cases. About 20 seconds.
- `scripts/quiet.sh` checks that nothing else is loading the machine before a benchmark.

Never benchmarked on: files from real data portals with ragged rows; inputs arriving in 4 KB reads from a pipe.
