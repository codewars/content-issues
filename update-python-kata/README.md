# FAQ: Update Python kata

## What is the problem with old Python kata?

The problem described here is caused by the fact that test suites of old kata do not conform to the form expected by Codewars code runner and produce test output in a format not conforming to the expected one. Main reason for that is that calls to assertions (`assert_equals`, `expect`, etc.) are not placed inside of an `@it` block, but in a scope of a `@describe` block or just in the toplevl scope of tests.

## Why eveything was OK until now, and now the problem suddenly popped up?

Because future compatibility and maintenance. Python is one of the oldest supported languages on Codewars and it drags behind a large bag of compatibility hacks and workarounds. Tests output is handled in the runner by mechanism which is not related to any programming language, and workarounds needed to make Python tests to work affect the maintainability of the runner overall. Tests output for majority of languages is well defined and structured, except a few which require a large set of workarounds, including Python.

Fixing tests will allow for cleaning up the code of the runner and will make it easier to devlop it, provide new features, and introduce new languages and language versions in the future.

## My kata work, do they have to be updated?

They should. Until they are, "old" format of tests output has to be supported, impeding updates to Python versions or test frameworks.

## Do I have to update my kata by myself?

No. It would be nice if Python authors and translators took responsibility of fixing kata and translations they created, but they are not forced to. However, autors should allow kata to get fixed by someone else. There's a group of users willing to fix affected kata, and they use available means to track them and update them. If you do not want to update kata on your own, let them do their work. Do not mark their issues as resolved if they are not, and do not obstruct their work.

## Will my kata stop working if they are not updated?

No. Codewars staff explicitly takes care to not leave kata broken when updating the code runner. If your kata would not work without being fixed, it will simply prevent the update or increase the efforts needed to roll one out.

## How can I update old kata?

There's a [reference of the new Python testing framework](https://docs.codewars.com/languages/python/codewars-test/#python-codewars-test-framework) and [tutorial on creating Python kata](https://docs.codewars.com/languages/python/authoring/#testing-framework) which contains some explanations and examples. We hope these will be helpful.

## I cannot update my kata, but I want to. What should I do?

You can just leave it, and someone will evntually handle it. You can also create an issue on [content issues board](https://github.com/codewars/content-issues/issues) so it would be hopefully processed sooner.
