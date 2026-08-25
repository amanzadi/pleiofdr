# pleioFDR V1 compatibility

## Status

The Apptainer definition, launcher, and Octave compatibility edits are in the
working tree. No SIF, demo run, MATLAB parity fixture, or benchmark result exists
in this repository yet.

## Rules

- Preserve the existing scientific pipeline: `config.txt`, MAT inputs, result
  files, CSV schemas, plots, options, and batch semantics.
- Run through `./pleiofdr-run [config.txt]`. The runtime is Apptainer or
  Singularity only; build `pleiofdr.sif` from `Apptainer.def` when needed.
- The SIF is runtime-only. The launcher mounts the checked-out repository and
  runs `runme.m` from it.
- Keep Python orchestration-only: invoke the launcher with `subprocess`.
  Do not add Python packaging, a Python-native API, or a scientific port in V1.
- Do not change scientific algorithms without a separate, reviewed release.
- Before release, build the SIF, run the demo, compare MATLAB parity fixtures,
  and benchmark the representative workload.
