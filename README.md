Purpose
=======
Running unit tests in a random order ensures that tests are isolated from eachother.  Come issues which break isolation are databases being left in with data in them at the end of one test being used in the next test.  When this happens simple changes to the first test may break the depenedent ones.


Installation
============
Add `randomize.py` to your project.  Then in your runner script simple `import randomize`.

Ask your test runner for help, ex. `runner.py --help`, and notice `--randomize` is now an option.


Usage
=====
The randomize plugin does not do anything unless `--randomize` is passed in.  When this flag is set the tests for each `TestCase` class will be randomly run.  When an isolation problem is found use the seed printed at the beginning of the test output to run the suite in the same *random* order.

```bash
# Run tests in random order
python runner.py --randomize
# stdout: Using 1234567890 as seed
```

```bash
# Run tests using a particular random ordering
python runner.py --randomize --seed=1234567890
```


Todo
====

 * Add tests
 * Randomize across TestCase classes


Initial code from
=================
http://code.google.com/p/python-nose/issues/detail?id=255


