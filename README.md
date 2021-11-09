[![say thanks](https://img.shields.io/badge/Say%20Thanks-👍-1EAEDB.svg)](https://github.com/DeveloperPaul123/periodic-function/stargazers)
[![Discord](https://img.shields.io/discord/652515194572111872)](https://img.shields.io/discord/652515194572111872)

# thread-pool

A simple, functional thread pool implementation using pure C++20.

## Features

* Built entirely with C++20
* Enqueue tasks with or without tracking results

## Usage

Simple example
```cpp
// create a thread pool with a specified number of threads.
dp::thread_pool pool(4);

// add tasks, in this case without caring about results of individual tasks
pool.enqueue_detach([](int value) { /*...your task...*/ }, 34);
pool.enqueue_detach([](int value) { /*...your task...*/ }, 37);
pool.enqueue_detach([](int value) { /*...your task...*/ }, 38);
// and so on..
```

## Buliding

This project has been built with:

* Visual Studio 202`2
* CMake `3.21+`

To build run:

```bash
cmake -S . -B build
cmake --build build
```

### Build Options

| Option | Description | Default |
|:-------|:------------|:--------:|
| `TP_BUILD_TESTS` | Turn on to build unit tests. Required for formatting build targets. | ON |
| `TP_BUILD_EXAMPLES` | Turn on to build examples | ON |

### Run clang-format

Use the following commands from the project's root directory to check and fix C++ and CMake source style.
This requires _clang-format_, _cmake-format_ and _pyyaml_ to be installed on the current system.

```bash
cmake -S test -B build/test

# view changes
cmake --build build/test --target format

# apply changes
cmake --build build/test --target fix-format
```

See [Format.cmake](https://github.com/TheLartians/Format.cmake) for details.

### Build the documentation

The documentation is automatically built and [published](https://developerpaul123.github.io/thread-pool) whenever a [GitHub Release](https://help.github.com/en/github/administering-a-repository/managing-releases-in-a-repository) is created.
To manually build documentation, call the following command.

```bash
cmake -S documentation -B build/doc
cmake --build build/doc --target GenerateDocs
# view the docs
open build/doc/doxygen/html/index.html
```

To build the documentation locally, you will need Doxygen and Graphviz on your system.

## Contributing

Contributions are very welcome. Please see [contribution guidelines for more info](CONTRIBUTING.md).

## License

The project is licensed under the MIT license. See [LICENSE](LICENSE) for more details.

## Author

| [<img src="https://avatars0.githubusercontent.com/u/6591180?s=460&v=4" width="100"><br><sub>@DeveloperPaul123</sub>](https://github.com/DeveloperPaul123) |
|:----:|
