# LLVM source for the Windows GPI compiler

- Upstream: https://github.com/llvm/llvm-project
- Fork: https://github.com/gggin/llvm-project
- Release: LLVM/Clang/LLD 20.1.8 (`llvmorg-20.1.8`).
- Upstream source commit: `87f0227cb60147a26a1eeb4fb06e3b505e9c7261`.
- West integration branch: `gpi-llvm-20.1.8`.
- Licenses and notices remain in the upstream source tree.

This version matches Zig 0.15.2's LLVM major version and release profile. GPI's
Windows compiler uses LLVM code generation and LLD's PE/COFF linker and import
library support. The application itself remains Zig. Linux retains its existing
compiler profile without LLVM; Darwin's existing explicit compiler policy remains.

The integration builds only the native X86 backend and the required Clang/LLD
libraries, with tests, examples and benchmarks disabled. Build artifacts and
development tools remain local and are never committed. GitHub Actions is disabled
for this fork; importing upstream workflows does not authorize running them.

Use the parent workspace's `gbig/scripts/build-windows-llvm.py` build helper.
