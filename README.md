# Java Simplified ☕

> Java beyond syntax: internals, patterns, performance, and engineering projects. My Java journey, documented in public so anyone can learn at the same depth.

![Java](https://img.shields.io/badge/Java-21-orange)
![Build](https://img.shields.io/badge/build-Maven-blue)
![Tests](https://img.shields.io/badge/tests-JUnit%205-green)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Status](https://img.shields.io/badge/status-in%20progress-yellow)

---

## Table of Contents

1. [Vision](#vision)
2. [Who This Is For](#who-this-is-for)
3. [How This Repo Works](#how-this-repo-works)
4. [Repository Structure](#repository-structure)
5. [Learning Roadmap](#learning-roadmap)
6. [Projects](#projects)
7. [Skills Matrix](#skills-matrix)
8. [Getting Started](#getting-started)
9. [Running Code](#running-code)
10. [Testing and Quality](#testing-and-quality)
11. [Conventions](#conventions)
12. [Companion Repositories](#companion-repositories)
13. [Contributing](#contributing)
14. [License](#license)

---

## Vision

This repo is a public record of how I learn and build in Java. It serves two purposes:

- **Portfolio:** every skill listed here is backed by code, benchmarks, or a project you can inspect.
- **Learning path:** every topic is written in my own words with runnable code, so anyone can follow the same order and reach the same depth.

The focus is on *how things actually work*, not just syntax: the JVM, the memory model, concurrency, collections internals, type system, design patterns, and performance. Each topic ends in something I built, not just something I read.

## Who This Is For

- **Recruiters and reviewers** who want evidence of skill, not claims.
- **Learners** who already know the basics and want depth and structure.
- **Engineers from other languages** who want to see how Java really behaves under the hood.
- **Me**, as a living reference I can return to.

## How This Repo Works

Every topic follows the same four-step loop:

| Step | Where | What happens |
|------|-------|--------------|
| 1. Understand | `curriculum/` | A written note: concept, why it exists, how it works, pitfalls |
| 2. Experiment | `learning-codes/` | Small runnable programs, benchmarks, internals demos |
| 3. Build | `projects/` | A project that applies the topic in a realistic setting |
| 4. Record | `SKILLS.md` | The skill is checked off with a link to the evidence |

## Repository Structure

```
java-simplified/
├── .github/
│   └── workflows/
│       └── ci.yml                # Build and test on every push
├── curriculum/                   # Concept notes, one per topic
│   ├── 01-language-core.md
│   ├── 02-oop-and-type-system.md
│   ├── 03-collections-internals.md
│   ├── 04-functional-java.md
│   ├── 05-jvm-and-memory.md
│   ├── 06-concurrency.md
│   ├── 07-io-and-networking.md
│   ├── 08-design-patterns.md
│   ├── 09-performance.md
│   ├── 10-testing-and-tooling.md
│   └── 11-spring-and-backend.md
├── learning-codes/               # Runnable experiments, grouped by topic
│   ├── 01_language_core/
│   ├── 02_oop_and_types/
│   └── ...
├── projects/                     # Self-contained projects, each with its own README
│   └── <project-name>/
├── src/
│   ├── main/java/com/javasimplified/   # Reusable utilities shared across topics
│   └── test/java/com/javasimplified/   # JUnit 5 tests
├── docs/
│   ├── setup.md                  # JDK, IDE, and tooling setup
│   └── benchmarks.md             # Collected benchmark results
├── .gitattributes
├── .gitignore
├── LICENSE
├── Makefile                      # Shortcuts for common commands
├── README.md
├── SKILLS.md                     # Evidence-linked skills matrix
└── pom.xml
```

## Learning Roadmap

Status key: ⬜ not started · 🟨 in progress · ✅ done

| Phase | Topic | Key areas | Status |
|-------|-------|-----------|--------|
| 01 | Language core | Types, operators, control flow, methods, strings, arrays, `var`, records, enums | ⬜ |
| 02 | OOP and type system | Classes, inheritance, interfaces, sealed types, generics, wildcards, type erasure | ⬜ |
| 03 | Collections internals | ArrayList, LinkedList, HashMap internals, TreeMap, ConcurrentHashMap, iteration contracts | ⬜ |
| 04 | Functional Java | Lambdas, functional interfaces, Streams, Collectors, Optional, laziness | ⬜ |
| 05 | JVM and memory | Class loading, bytecode, heap and stack, garbage collectors, JIT, memory model | ⬜ |
| 06 | Concurrency | Threads, synchronization, `java.util.concurrent`, CompletableFuture, virtual threads | ⬜ |
| 07 | I/O and networking | NIO, files, sockets, HTTP client, serialization | ⬜ |
| 08 | Design patterns | Creational, structural, behavioral, and where they fit in modern Java | ⬜ |
| 09 | Performance | JMH benchmarking, profiling, allocation analysis, tuning flags | ⬜ |
| 10 | Testing and tooling | JUnit 5, Mockito, property tests, Maven and Gradle, static analysis | ⬜ |
| 11 | Spring and backend | Spring Boot, REST APIs, persistence, security basics, deployment | ⬜ |

## Projects

| Project | Applies | Description | Status |
|---------|---------|-------------|--------|
| _coming soon_ | | | ⬜ |

Each project lives in `projects/<name>/` with its own README covering: problem, design decisions, how to run it, and what I learned.

## Skills Matrix

The full, evidence-linked checklist lives in [SKILLS.md](SKILLS.md). Each skill links to the code, test, benchmark, or project that proves it.

Levels used:

| Level | Meaning |
|-------|---------|
| 1 | Can explain it |
| 2 | Can use it with references |
| 3 | Can use it independently and debug it |
| 4 | Can design with it and justify trade-offs |

## Getting Started

### Prerequisites

- JDK 21 or newer (`java -version`)
- Maven 3.9+ (`mvn -v`)
- Git
- Any IDE: IntelliJ IDEA, VS Code with the Java extension pack, or Eclipse

Detailed setup steps are in [docs/setup.md](docs/setup.md).

### Clone

```bash
git clone https://github.com/yashvardhansingh442-dev/java-simplified.git
cd java-simplified
```

### Build

```bash
mvn compile
```

## Running Code

**Single-file experiments** (no build step needed):

```bash
java learning-codes/01_language_core/HelloWorld.java
```

**Code under `src/`:**

```bash
mvn exec:java -Dexec.mainClass="com.javasimplified.Main"
```

**Using the Makefile:**

```bash
make build            # compile
make test             # run all tests
make run file=learning-codes/01_language_core/HelloWorld.java
make clean            # remove build output
```

## Testing and Quality

- **Tests:** JUnit 5, run with `mvn test`.
- **CI:** GitHub Actions runs `mvn verify` on every push and pull request.
- **Benchmarks:** JMH for performance claims. Results are recorded in [docs/benchmarks.md](docs/benchmarks.md) with the JDK version and hardware noted.
- **Principle:** a performance or behavior claim in the notes should be backed by a test or benchmark in this repo.

## Conventions

- **Notes:** each `curriculum/` file follows the same template: *Concept → Why it exists → How it works → Pitfalls → Code links → Further reading*.
- **Code:** one concept per file, with a short comment header explaining the goal and expected output.
- **Naming:** `snake_case` for folders, `PascalCase` for Java classes, numeric prefixes to keep learning order.
- **Commits:** short and descriptive, using the form `type: message`, for example `docs: add HashMap internals note` or `feat: add LRU cache project`.
- **Branches:** work happens on `main` for now; larger projects may use feature branches.

## Companion Repositories

- **[python-deep-dive](https://github.com/yashvardhansingh442-dev/python-deep-dive):** the Python counterpart, focused on language internals, advanced features, and applied depth.

## Contributing

This is primarily a personal learning log, but corrections and suggestions are welcome:

- Found a factual error in a note? Open an issue or a pull request.
- Have a better explanation or a useful reference? Suggest it in an issue.
- Please keep changes focused and explain the reasoning.

## License

Released under the [MIT License](LICENSE). Free to use, learn from, and share.

---

*Built in public, one concept at a time.*
