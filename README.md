pytest-readme
=============

A pytest plugin to pull out tests from your README.md into pytest automatically. This will make it easy to make sure your readme doesn't contain any errors.

Usage
=====

First `pip install pytest-readme`, then create a `conftest.py` file in the same directory as your README.md and put the following two lines in it:

```python

from pytest_readme import setup
setup()
```

pytest-readme will generate a file called `test_readme.py`, so you probably want to add that to your `.gitignore` file. 

pytest-readme supports two formats of tests: 
* doctest style
* pytest style

Note also that any blocks of python code without asserts is treated as pytest style test, so the code will be executed in a test. This is useful for at least checking that the functions exists, the parameters are in the correct order and that exceptions aren't raised.

Doctest style:

```python
>>> 1 + 1
2
```

Pytest style:

```python
assert 1 + 1 == 2
```

To avoid running a block of code from your readme, just make sure you have an empty line first. This won't show in in the markdown render and pytest-readme will skip the block.

Badge
=====

You can show that your README is tested with this badge: [![Examples tested with pytest-readme](http://img.shields.io/badge/readme-tested-brightgreen.svg)](https://github.com/boxed/pytest-readme) Copy paste the markdown syntax below:

    [![Examples tested with pytest-readme](http://img.shields.io/badge/readme-tested-brightgreen.svg)](https://github.com/boxed/pytest-readme)
