[![CI_Matrix_test](https://github.com/nogibjj/Mobasserul_Haque_Week4_Matrix_Build/actions/workflows/CI_Matrix_test.yml/badge.svg)](https://github.com/nogibjj/Mobasserul_Haque_Week4_Matrix_Build/actions/workflows/CI_Matrix_test.yml)

# GitHub Actions Matrix Build for Multiple Python Versions and OS

This project showcases how to use GitHub Actions to set up a matrix build for testing Python code across different Python versions and operating systems. The project includes a simple `palindrome checker` implementation with `unit tests`, and utilizes a `Makefile` for managing tasks like dependency `installation`, code `formatting`, `linting`, and `testing`.

## Project Structure

- `palindrome_checker.py`: Contains the `is_palindrome` function, which checks if a given word is a palindrome.
- `test_palindrome_checker.py`: Unit tests for the `is_palindrome` function using Python’s `unittest` framework.
- `Makefile`: Defines tasks for installing dependencies, formatting code, linting, and running tests.

## GitHub Actions Workflow

The GitHub Actions workflow (`.github/workflows/CI_Matrix_test.yml`) runs automatically on:

- Pushes to the `main` branch.
- Pull requests targeting the `main` branch.
- Manual triggers via `workflow_dispatch`.

![Matrix_Build_multiple_version_run][CI_Matrix_test_build.PNG]

### Workflow Details

The workflow builds the project on multiple Python versions and operating systems using a matrix configuration:

- **Python versions**: 3.7, 3.9, 3.10.11, 3.11, 3.12
- **Operating systems**: Ubuntu-latest, Windows-latest

### Workflow Steps

1. **Checkout code**: Clones the repository to the runner.
2. **Set up Python**: Configures the Python version based on the matrix configuration.
3. **Install dependencies**: Installs the required packages using `make install`.
4. **Lint code**: Lints the Python code using `make lint`.
5. **Run tests**: Runs the unit tests with `make test`, including code coverage.
6. **Format code**: Formats the code using `make format`.

## Makefile

The `Makefile` includes commands to streamline the development process:

- **install**: Installs the necessary dependencies from `requirements.txt`.
- **format**: Formats the Python files using Black.
- **lint**: Lints the code with Pylint, ignoring some warning categories.
- **test**: Runs the test suite using `pytest` with coverage reporting.
- **all**: Runs all tasks (install, format, lint, and test).

### Usage

To run the tasks locally, you can use the following commands:

```bash
# Install dependencies
make install

# Format code
make format

# Lint code
make lint

# Run tests
make test
