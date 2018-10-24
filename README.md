# Consoleation
[![Build Status](https://travis-ci.org/blesta/module-cwatch.svg?branch=master)](https://travis-ci.org/blesta/module-cwatch) 

A simple library for output to command-line and setting a progress bar

## Installation
Install via Composer

```
composer require blesta/consoleation
```

## Basic Usage

### Retrieve a single line from standard input

```
use Blesta/Consoleation;

$console = new Consoleation();
$line = $console->getLine();
```

### Display content to standard output

```
use Blesta/Consoleation;

$console = new Consoleation();
$console->output("This is a single line\n");
```

Any number of additional arguments may be passed to _output_ to perform string replacements via `sprintf`.

```
use Blesta/Consoleation;

$console = new Consoleation();
$console->output("Would you like %s or %s?", "apples", "oranges");
```

### Display a progress bar

```
use Blesta/Consoleation;

$console = new Consoleation();
$console->output("Performing the installation...\n");

$start = 1;
$finish = 1000;
$progressBarCharLength = 50;
foreach (range($start, $finish) as $index => $number) {
  $console->progressBar($index + 1, $finish, $progressBarCharLength);
}
```
