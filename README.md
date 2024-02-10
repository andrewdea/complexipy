# complexipy

An extremely fast Python library to calculate the cognitive complexity of
python files, written in Rust.

## Getting Started

### Installation

**complexipy** is available as
[`complexipy`](https://pypi.org/project/complexipy/) on PyPI (Python >= 3.11):

```bash
pip install complexipy
```

### Usage

To run **complexipy** you can use the following command:

<pre lang="shell">
<b>complexipy</b> .                         # Use complexipy to analyze the current directory and any subdirectories
<b>complexipy</b> path/to/directory         # Use complexipy to analyze a specific directory and any subdirectories
<b>complexipy</b> path/to/file.py           # Use complexipy to analyze a specific file
<b>complexipy</b> path/to/file.py -m 20     # Use the -m option to set the maximum congnitive complexity, default is 15
</pre>

For example, given the following file:

```python
def a_decorator(a, b):
    def inner(func):
        return func
    return inner

def b_decorator(a, b):
    def inner(func):
        if func:
            return None
        return func
    return inner
```

The cognitive complexity of the file is 3, and the output of the command
`complexipy path/to/file.py` will be:

```bash
───────────────── complexipy 0.1.0 🐙 ─────────────────
test_decorator.py
Analysis completed! 🎉
                  Summary
┏━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━┓
┃ File              ┃ Cognitive Complexity ┃
┡━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━┩
│ test_decorator.py │ 1                    │
└───────────────────┴──────────────────────┘
Total files: 1
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file
for details.

## Acknowledgments

- This project is inspired by the sonar way to calculate the cognitive
complexity.

## References

- [Cognitive Complexity](https://www.sonarsource.com/resources/cognitive-complexity/)
