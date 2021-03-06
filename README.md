dart-coveralls
==============
[![Coverage Status](https://coveralls.io/repos/Adracus/dart-coveralls/badge.png)](https://coveralls.io/r/Adracus/dart-coveralls)

Calculate coverage of your dart scripts, format it to LCOV and send it to
[coveralls.io](https://coveralls.io/).

### Usage
This package consists of a single command line tool `dart_coveralls` with
the three commands `calc`, `report` and `send`.

#### The `calc` command
This command calculates the coverage of a given package. Use the tool like this:

```
dart dart_coveralls.dart calc [--workers, --output, --package-root] test.dart
```

* `--workers`: The number of workers used to parse LCOV information
* `--output`: The output file path, if not given stdout
* `--package-root`: The root of the analyzed package, default `.`
* `test.dart`: The path of the test file on which coverage will be collected

#### The `report` command
This command calculates and then sends the coverage data to coveralls.io. Usage
of the tool is as follows:

```
dart dart_coveralls.dart report [--workers, --token, --package-root, --debug, --retry] test.dart
```

* `--workers`: The number of workers used to parse LCOV information
* `--token`: The token for coveralls.io. The token can also be set as an
  environment variable called `REPO_TOKEN`.
* `--package-root`: The root of the analyzed package, default `.`
* `--debug`: Prints additional debug information
* `--retry`: The number of retries to submit data to coveralls
* `test.dart`: The path of the test file on which coverage will be collected

#### The `send` command
This command sends coverage collected in an LCOV-File to coveralls.io.

```
dart dart_coveralls.dart send [--token, --package-root, --retry] lcov.file
```

* `--token`: The token for coveralls.io. The token can also be set as an
  environment variable called `REPO_TOKEN`.
* `--package-root`: The root of the analyzed package, default `.`
* `--retry`: The number of retries to submit data to coveralls
* `lcov.file`: The LCOV file which should be reported to coveralls

### Contributing

Help and Pull Requests are highly appreciated :)
