# Repository instructions

## macOS test safety

- Never configure, build, or run the `native-sanitized` CMake preset on macOS.
- Do not run binaries from `out/build/native-sanitized` on macOS. The sanitizer runtime can hang and leave CPU-consuming test processes behind.
- On macOS, use `native-debug` and `ctest --preset native-debug --output-on-failure` for the native test suite.
- Run sanitizer presets only in a known-safe non-macOS environment or CI job.
- If a macOS sanitizer command is started accidentally, identify and stop its `ctest` and `game_rules_candidate_*` processes before continuing.
