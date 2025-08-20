https://github.com/MasonMartinez1/ap-e2025-pub/releases

# Advanced Programming E2025 — Public Labs, Scripts, and Examples

[![Releases](https://img.shields.io/badge/Releases-download-blue?logo=github&style=for-the-badge)](https://github.com/MasonMartinez1/ap-e2025-pub/releases)

🧠 🛠️ 📚 🚀

A public repository that collects code, labs, exercises, and reference material for Advanced Programming (E2025). The content targets students, instructors, and developers who work with systems programming, concurrency, testing, and tooling. The repo groups small projects, scripts, and examples that align with a modern course on advanced programming.

Cover image  
![Programming workspace](https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1600&q=80)

Table of contents
- About this repo
- What you will find
- Releases and how to run assets
- Quick start
- Core examples and labs
- Development workflow
- Testing and CI
- Project layout
- How to contribute
- License and contact

About this repo
This repository serves as a public archive for course material and demos for Advanced Programming. It collects small, focused units that demonstrate core topics such as:
- Concurrency and parallelism
- Memory safety and low-level interfaces
- Networked services and protocols
- Build systems and automation
- Debugging and profiling
- Unit and integration testing

Each unit contains code, a brief writeup, and a reproducible test. The code favors clarity and strong tests over long features.

What you will find
- Short labs with exercises and solutions in multiple languages.
- Scripts to build, run, and check examples.
- Dockerfiles and container images for isolation.
- CI config and test harnesses.
- Reference notes that explain trade-offs and patterns.
- Release artifacts for runnable binaries and installers.

Releases and how to run assets
The Releases page hosts compiled assets and packaged examples. Download the release file that matches your platform and execute it.

- Visit the Releases page via the badge at the top or the raw link at the start of this document.
- Pick the asset for your OS (linux, macos, windows).
- Download the asset and run the file for the demo you want to try.
- For archive assets, extract the archive, then run the included run script or binary.

Quick start
Follow these steps to run a sample demo from a release asset.

1. Choose a release asset that matches your platform from the Releases page.
2. Download the file to a local folder.
3. On Unix-like systems:
   - Make the binary executable: chmod +x ./my-demo
   - Run: ./my-demo
4. On Windows:
   - Unpack the archive if needed.
   - Double-click the executable or run from PowerShell: .\my-demo.exe
5. Follow any runtime instructions that appear in the demo console.

If a release contains a packaged example with a run script, run the script after extraction. The Releases page will contain a short changelog and the asset name for each release.

Core examples and labs
This section lists representative examples with usage notes and goals.

1) Concurrency lab — thread-pool and actor demos
- Goal: Compare thread pools and actor models.
- What you get: worker pool implementation, benchmark scripts, test harness.
- Run: use the provided benchmark binary from the release or run the test suite in the repo.

2) Systems interface — FFI and memory layout
- Goal: Show safe FFI patterns and memory layout checks.
- What you get: small C program, Rust and Python wrappers, test cases.
- Run: compile the C example or use the precompiled release asset.

3) Network lab — small HTTP server and client
- Goal: Demonstrate non-blocking I/O and request routing.
- What you get: server code, load test script, TLS demo.
- Run: launch the server binary and then run the client load test included in the release.

4) Build and tooling — Make, Ninja, and Bazel examples
- Goal: Show build graphs and incremental builds.
- What you get: build configs, analysis scripts, caching demo.
- Run: invoke the build script or use the packaged CI environment from the release.

5) Debugging and profiling
- Goal: Walk through native profiling and allocation tracing.
- What you get: sample workloads, perf scripts, flamegraph generator.
- Run: run the profiling script in the release and open generated flamegraphs in a browser.

Development workflow
The repo uses a small, repeatable workflow. Follow these steps to add new content.

1. Create a branch named feature/<short-name>.
2. Add a single unit: code, README for the unit, tests, and a simple run script.
3. Keep commits small and focused.
4. Add tests that cover intended behavior and edge cases.
5. Open a pull request and tag the PR with the unit topic.

Use language-native tooling for formatting and linting. Examples include:
- gofmt or go vet for Go
- rustfmt and clippy for Rust
- flake8 and pytest for Python
- clang-format for C/C++

Testing and CI
The repo includes CI templates that run tests and build release artifacts. Tests run in containerized environments to ensure consistent results.

Local test tips:
- Use the included Dockerfiles to create a local test environment.
- Run unit tests with the language test runner.
- For integration tests, run the provided harness that spins up local services.

Continuous integration covers:
- Static checks and linters
- Unit tests
- Build steps that produce release artifacts

Project layout
The repository keeps a flat, modular layout so each unit stands alone.

- /labs
  - Each lab in its own folder with a README, code, and tests.
- /scripts
  - Build, run, and test helper scripts for local work.
- /ci
  - CI templates and pipeline definitions.
- /releases
  - Release notes and changelogs (source only; binaries live on the Releases page).
- /docs
  - Short notes that explain the patterns used across labs.
- /tools
  - Small utilities that support demos and tests.

Each lab follows this pattern:
- code/         -> source files
- test/         -> unit and integration tests
- run.sh        -> script to run the demo locally
- README.md     -> what the lab teaches and how to run it

How to contribute
Contributions follow a simple pattern. You can propose new labs, fix issues, or improve docs.

- Fork the repo.
- Create a branch for your change.
- Add tests for new behavior.
- Keep changes focused.
- Submit a pull request with a clear description and the goal of the change.

Use clear commit messages and reference relevant issue numbers when applicable. For larger contributions, open an issue to discuss the design before implementing.

Coding guidelines
- Prefer small, testable functions.
- Write tests that assert behavior, not implementation.
- Keep external dependencies minimal.
- Document build and runtime steps in the lab README.

Release policy
Releases contain packaged binaries and a changelog. The release naming uses semantic versioning. Each release includes:
- release notes describing changes
- artifacts built for common platforms
- checksums for artifact integrity

Find releases via the badge at the top or the raw link at the top of this file. Download the asset for your platform and execute it as described in the Releases and how to run assets section.

Examples and snippets
Use the following snippets as a reference when writing labs.

Run a demo script (Unix):
```bash
# make sure the run script is executable
chmod +x ./run.sh
./run.sh
```

Run tests (example for Python):
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pytest -q
```

Run a containerized test:
```bash
docker build -t ap-e2025-lab .
docker run --rm ap-e2025-lab ./run-tests.sh
```

Best practices for lab authors
- Keep each lab self-contained.
- Provide automated checks.
- Provide sample inputs and expected outputs.
- Use clear README with steps to reproduce results.

Common patterns demonstrated
- Producer-consumer queues with bounded buffers.
- Structured concurrency patterns for task lifetimes.
- Safe interfaces across FFI boundaries.
- Effective test harnesses that use fixtures and mocks.
- Reproducible builds with pinned toolchains.

Contact and support
Report problems by opening issues on the repository. For code reviews and questions, open a discussion thread or a pull request that requests feedback.

Licensing
Most code in this repository uses a permissive license. Check the LICENSE file in the repo root for the exact terms.

Files to check first
- labs/README.md — overview of available labs
- scripts/bootstrap.sh — local setup helper
- ci/pipeline.yml — CI pipeline to run tests and build releases
- docs/patterns.md — short explanations of the main patterns used across labs

Images and diagrams
The docs folder contains diagrams that explain architecture and data flow for select labs. Those diagrams come in SVG and PNG formats for use in slides and reports.

Acknowledgments
This repository draws on common patterns from systems programming and testing literature. It compiles numerous small examples to help learners build intuition and skills.

Keep contributions focused on pedagogy and reproducible examples. Build small units that run in isolation and include tests that validate the expected behavior.