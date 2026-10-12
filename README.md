# COMP Virtual File System

**COMP2021 — Object-Oriented Programming Course Project （2024）**

A command-line virtual file system implemented in Java. It supports creating and managing virtual disks, directories, and documents; recursive listing and criterion-based search; saving and loading disk states; and undo/redo operations.

**Technologies:** Java, object-oriented design, the Command pattern, Java serialization, and JUnit 4.

## Repository Structure

- `src/`: application source code, preserving the Java package hierarchy.
- `test/`: JUnit tests.
- `lib/`: bundled JUnit and Hamcrest dependencies.
- `docs/`: [user manual](docs/OOP%20User%20Manual.pdf), [project report](docs/OOP%20Report.pdf), and [presentation](docs/Slides.pdf).
- `examples/`: existing serialized virtual-disk snapshots (`path1` and `testpath`).
- `cvfs.iml`: original IntelliJ IDEA module configuration.

## Build and Run

With a JDK installed, run these commands from the repository root (macOS/Linux):

```bash
mkdir -p build/classes
find src -name '*.java' > build/sources.txt
javac -d build/classes @build/sources.txt
java -cp build/classes hk.edu.polyu.comp.comp2021.cvfs.Application
```

The application displays its available commands on startup. Enter `quit` to exit; consult the user manual for command syntax.

## Tests

```bash
mkdir -p build/test-classes
find test -name '*.java' > build/tests.txt
javac -cp 'build/classes:lib/*' -d build/test-classes @build/tests.txt
java -cp 'build/classes:build/test-classes:lib/*' org.junit.runner.JUnitCore hk.edu.polyu.comp.comp2021.cvfs.model.CVFSTest
```

Some existing tests compare exact console output and may depend on platform-specific line endings. The save/load test writes `testpath` in the working directory.
