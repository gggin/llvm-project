# LLVM source for native GPI compilers

- Upstream: https://github.com/llvm/llvm-project
- Fork: https://github.com/gggin/llvm-project
- Release: LLVM/Clang/LLD 20.1.8 (`llvmorg-20.1.8`).
- Upstream source commit: `87f0227cb60147a26a1eeb4fb06e3b505e9c7261`.
- West integration branch: `gpi-llvm-20.1.8`.
- Licenses and notices remain in the upstream source tree.

This version matches Zig 0.15.2's LLVM major version and release profile.
Linux x86_64, Windows x86_64 and macOS x86_64/arm64 all build the same owned
LLVM/Clang/LLD source. GPI uses LLVM code generation, Clang C imports and LLD
native linking on each platform. Application and snippet sources remain Zig.

The integration builds X86 on x86_64 hosts and AArch64 on Apple Silicon,
including the required Clang/LLD libraries, with tests, examples and benchmarks
disabled. Build artifacts and development tools stay in ignored local caches.
The compiler statically links these libraries and retains their notices.
GitHub Actions remains disabled; importing upstream workflows does not authorize
running them.

Use `gbig/scripts/build-llvm.py` on each native host. It prepares per-platform
compiler configurations in `zig-gpi/.zig-cache/gpi-llvm-cmake/<os>-<arch>/`.
The existing `build-windows-llvm.py` entry point remains a compatibility wrapper.
