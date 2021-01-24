# FAQ: Update Python kata

## What is the problem with old Python kata?

The problem described here is caused by the fact that test suites of old kata do not conform to the form expected by Codewars code runner and produce test output in a format not conforming to the expected one. The main reason for that is that calls to assertions (`assert_equals`, `expect`, etc.) are not placed inside of an `@it` block, but in a scope of a `@describe` block or just in the top-level scope of tests.

Additionally, missing imports for test framework and solution modules make some additional preprocessing necessary and potentially mess up line numbers in error messages.

## Why was everything OK until now, and now the problem suddenly popped up?

Because of future compatibility and maintenance. Python is one of the oldest supported languages on Codewars and it drags behind a large bag of compatibility hacks and workarounds. The test output is handled in the runner by a mechanism that is not related to any programming language, and workarounds needed to make Python tests work affect the maintainability of the runner overall. Test output for the majority of languages is well defined and structured, except a few which require a large set of workarounds, including Python.

Fixing tests will allow for cleaning up the code of the runner and will make it easier to develop it, provide new features, and introduce new languages and language versions in the future.

Additionally, from the user perspective, improperly structured tests tend to result in poor output and are prone to buggy display in test output panel. Updating the kata can potentially fix erlated problems.

## My kata work, do they have to be updated?

They should be. Until they are, the "old" format of the test output has to be supported, impeding updates to Python versions or test frameworks.

## Do I have to update my kata by myself?

No. It would be nice if Python authors and translators took the responsibility for fixing kata and translations they created, but they are not forced to. However, authors should allow kata to get fixed by someone else. There's a group of users willing to fix affected kata, and they use available means to track them and update them. If you do not want to update kata on your own, let them do their work. Do not mark their issues as resolved if they are not, and do not obstruct their work.

## Will my kata stop working if they are not updated?

No. The Codewars staff explicitly take care to not leave kata broken when updating the code runner. When any change is going to be introduced, it will be done in a backwrds compatible way. However, if your kata would not work without being fixed, it will simply postpone the update or increase the efforts needed to roll one out.

## How do I update old kata?

Basically you need to do two things:
 - make sure that all assertions are called inside of a function decorated with `@it`,
 - add missing imports for `solution`, `codewars_test`, and `preloaded` modules if necessary, to the full tet suite and sample tests (and `preloaded` to example solution, if necessary).

There's a [reference of the new Python testing framework](https://docs.codewars.com/languages/python/codewars-test/#python-codewars-test-framework) and [tutorial on creating Python kata](https://docs.codewars.com/languages/python/authoring/#testing-framework) which contains some explanations and examples. We hope these will be helpful.

It would be great if some other, existing issues were also addressed, in the one go.

If you write a post in kata discussion to get attention of its author or to signal the neccessity of update, consider using `suggestion` label instead of `issue`. After the kata is updated, it would be nice to thank the author or mainainer for handling it.

## I cannot update my kata, but I want to. What should I do?

You can just leave it, and someone will eventually handle it. You can also create an issue on [content issues board](https://github.com/codewars/content-issues/issues) so it would be hopefully processed sooner.
