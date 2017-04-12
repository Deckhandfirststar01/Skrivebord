# README

Functional specification for all products (hopefully someday soonish) at eyeo.

## License

Copyright (C)  2017  eyeo GmbH.

Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.3
or any later version published by the Free Software Foundation;
with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
A copy of the license is included in the section entitled "GNU
Free Documentation License".

[GNU Free Documentation License](/COPYING)

## File structure

- `/spec/PRODUCT/` markdown source files go here
- `/res/PRODUCT/` images and other resources go here
- `/doc/` documentation goes here

## Local development preview

You can preview your local changes using [grip](https://github.com/joeyespo/grip)

```bash
$ cd specrepo
$ grip
 * Running on http://localhost:6419/
```

Then point your browser to the file you want to preview <http://localhost:6419/spec/PRODUCT/filename.md>

## Resources

- [How to spec](/doc/how-to-spec.md) Guide on how to write functional specifications
- [How to setup grip and bitbucket on osx](/doc/grip-bitbucket-osx.md) Guide on how to setup [grip](https://github.com/joeyespo/grip) and [github](https://github.com) on osx
- [How to edit the spec using git](/doc/git-basics.md) Guide on how to edit the specification using git
- [How to link to a specific version](/doc/git-basics.md#markdown-header-how-to-link-to-a-specific-version) How to get a link to a specific version (for use in tickets)
- [Working with WIP commits](/doc/git-basics.md#markdown-header-working-with-wip-commits) How to temporarily commit you changes to work on another branch
- [Markdown style guide](http://www.cirosantilli.com/markdown-style-guide/)
  Markdown styleguide to help you produce better markdown files


