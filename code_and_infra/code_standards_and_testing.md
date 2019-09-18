Depending on the languages you use, you should have loose standards for code in each language. You should have tooling to test compliance, and usually this tooling should also be capable of running tests on code.

# Governance of standards
Your developers will have opinions on the tools and coding styles, and they may be frustrated if there appear to be no way to either get exemptions for their projects or to change these decisions.
Your standards should not be strict - if a developer (or particularly a team) has a reason to want a certain tool for their project, or to exempt part of a codebase from a tool, let them. Avoid tools that are highly opinionated that don't permit an out (such as the Black code formatter).
For changing the standards themselves, consider having a regular meeting every 6 months with a fixed set of people and to let people with concerns or proposals attend that meeting and press for change.

# Local coding style
It is fine to have a local coding style. Document it, and make config files available for code tooling that use it (e.g. settings for eclipse, vim, and gnu indent). When your company is big enough, it should have a developer tools team that has this as one of its responsibilities (maintaining CI systems is another).
In a sufficiently large company, letting teams also have their local coding style can make sense (especially if they are using their chosen language in ways
that are quite different from normal use, e.g. a Ruby shop that also uses Chef.

# Linters, Formatters, and Checkers
For teams not working on a quick prototype, these tools are essential to keep code in a largely consistent style and to find bugs. Sometimes this should be run by users, sometimes by a revision control system, and sometimes both.
Spend time finding tools you like for your language. Some languages, like Go, have a lot of these tools built-in.

For Python, consider:
* yapf - Code formatter
* nose - Testing framework
* mypy - Type annotation checker

Whatever tools you pick should have ways to disable checks on certain blocks of code. Do not forbid developers from doing this.

# Continuous integration
When possible, you should have your revision control system have diffs/pull-requests run through some automated testing before merging.
Standard tests that apply to all code in a language are fine, but developers also should be able to write their own tests, and trained in doing so.

Jenkins and Travis are both good tools to this end and integrate well with Github; GitHub Actions as of 2019 became capable of running checks natively.
