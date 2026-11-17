# siltcsv

A CSV parser in Rust that aims to be the fastest correct one. About 2.9 GB/s on the dev corpus on the reference
machine (Ryzen 7950X), single thread.

- `src/`: the parser (`scan.rs` SIMD delimiter scan, `quote.rs` quote state, `chunk.rs` parallel chunking, `field.rs` field arena).
- `bench/README.md`: how to benchmark, and the two corpora.
- `docs/tried.md`: every optimisation tried, kept or not.
- `docs/open_questions.md`: timings we cannot explain.
- `tests/conformance/`: 1,912 conformance cases. All must pass.

Maintainer: Joss.
