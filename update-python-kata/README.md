# FAQ: Update Python kata

## What is the problem with old Python kata?

The problem described here is caused by the fact that test suites of old kata do not conform to the form expected by Codewars code runner and produce test output in a format not conforming to the expected one. Main reason for that is that calls to assertions (`assert_equals`, `expect`, etc.) are not placed inside of an `@it` block, but in a scope of a `@describe` block or just in the toplevl scope of tests.

## Why eveything was OK until now, and now the problem suddenly popped up?

Because future compatibility and maintenance. Python is one of the oldest supported languages on Codewars and it drags behind a large bag of compatibility hacks and workarounds. Tests output is handled in the runner by mechanism which is not related to any programming language, and workarounds needed to make Python tests to work affect the maintainability of the runner overall. Tests output for majority of languages is well defined and structured, except a few which require a large set of workarounds.

Fixing tests will allow for cleaning up the code if the runner and will make it easier to devlop it, provide new features, and introduce new languages and language versions in the future.

## Do my kata have to be updated?

They should. Until they are, "old" format of tests output has to be supported, impeding updates to Python versions or test frameworks.

## Do I have to update my kata?

No. It would be nice if Python authors and translators took responsibility of fixing kata and translations they created, but they are not forced to.

## Will my kata stop working if they are not updated?

## How can I update old kata?
