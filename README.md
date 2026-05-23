# Markov Text Generator

A Java command-line text generator that trains on an input text file and then produces a sequence of words starting from a seed word. `TextGenerator` is the abstract entry point and dispatches to one of three strategies: `DeterministicGenerator` (always picks the most frequent successor, breaking ties lexicographically), `RandomGenerator` (samples successors weighted by frequency), and `ProbabilisticGenerator` (returns the top-k most probable successors).

## What's in here

- `src/main/java/TextGenerator.java` — abstract base class and `main` dispatcher
- `src/main/java/DeterministicGenerator.java` — most-frequent-successor strategy
- `src/main/java/RandomGenerator.java` — frequency-weighted random sampling
- `src/main/java/ProbabilisticGenerator.java` — top-k most-probable successors

## Requirements

- JDK 17
- Gradle (the bundled `gradlew` wrapper handles this)

## How to build & run

```bash
./gradlew build
./gradlew run --args="<input-file> <seed-word> <how-many> <deterministic|random|probable>"
```

On Windows:
```powershell
.\gradlew.bat build
.\gradlew.bat run --args="<input-file> <seed-word> <how-many> <deterministic|random|probable>"
```

In IntelliJ: open the folder, let Gradle sync, then run the `main` method in `TextGenerator` with program arguments matching the four positional parameters above.

## How to use

Pass four command-line arguments: a training text file, a seed word, the number of words to generate, and the generation strategy (`deterministic`, `random`, or `probable`). The chosen generator trains on the file and prints the generated sequence to stdout.

## Origin

Originally a coursework assignment; pulled out as a standalone repo.
