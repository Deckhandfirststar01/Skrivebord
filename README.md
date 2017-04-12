# README

Functional specification for all products (hopefully someday soonish) at eyeo.

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
- [How to link to a specific version](/doc/git-basics.md#how-to-link-to-a-specific-version) How to get a link to a specific version (for use in tickets)
- [Working with WIP commits](/doc/git-basics.md#working-with-wip-commits) How to temporarily commit you changes to work on another branch
- [Markdown style guide](http://www.cirosantilli.com/markdown-style-guide/)
  Markdown styleguide to help you produce better markdown files
