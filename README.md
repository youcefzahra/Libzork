# 📚 Libzork - C++ Interactive Fiction Engine

> **Showcase Repository:** To comply with EPITA's anti-plagiarism regulations, the raw source code of this engine is kept private. This repository serves as a technical showcase of modern C++ software architecture and graph-based narrative logic.

## 📖 Project Overview

**Libzork** is a modular C++20 engine designed to parse and execute branching "Choose Your Own Adventure" stories. The engine builds a directed graph representation of the narrative in memory, where nodes represent scenes and choices represent the edges linking them.

## 🏗️ Technical Architecture

The project follows high-level software engineering standards and modern C++ idioms:

* **Interface/Implementation Pattern:** To provide a stable public API, core classes (Node, Story, Store) are defined as pure virtual interfaces in public headers, with private implementations (Impl) hidden in the source directory.
* **Memory Safety:** The engine utilizes strict ownership rules through `std::unique_ptr` and factory patterns, ensuring exception-free resource management.
* **Decoupled Logic:** Narrative data (the Story graph) is entirely decoupled from the execution contexts (Runners), allowing for multiple interfaces (CLI, Interactive, or HTML output) without altering the core engine.

## ✨ Key Features

* **Dynamic Story Graph:** Supports complex narrative paths with cyclic loops and terminal nodes.
* **State Management:** Advanced system for variables, conditional choices, and actions that modify the world state.
* **Advanced Runners:**
    * **Choice Runner:** Classic numbered menu navigation.
    * **Smart Runner:** Natural language processing using a synonym dataset for sentence similarity.
* **Persistence & History:** Full support for **Undo/Redo** operations and **Save/Restore** functionality via YAML snapshots.

## 🎯 Testing the Engine

A pre-compiled demo is available in the **Releases** section.

1. Download and extract the `libzork_demo.tar.gz` archive:
```bash
tar -xvf libzork_demo.tar.gz
cd libzork_demo
```

2. Ensure your library path includes the current directory and run the explorer:
```bash
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:.
./zorkxplorer --story tests/stories/short_static/story.yml
```
