# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

## Question

**Q:** What happens when the executable is linked statically? Does Valgrind still detect the same bugs? Why or why not?

When an executable is linked statically, Valgrind can still detect memory-related issues like leaks and invalid memory accesses. Valgrind's effectiveness remains unchanged because its memory tracking isn't dependent on the linking method. However, some issues that require static analysis may not be detected by Valgrind, regardless of the linking method used.

