# Resume

LaTeX source for my personal resume linked on [chris.santamaria.me](https://chris.santamaria.me/). Uses a GitHub Actions workflow for automatic PDF builds uploaded as releases.

## Actions Workflow

The action is triggered on a version tag push. To tag changes and push with a tag to GitHub:

```
git tag v1.0.0
git push --follow-tags
```

The repository is first cloned using [actions/checkout](https://github.com/actions/checkout). Next, [latex-action](https://github.com/xu-cheng/latex-action) is triggered to compile `resume.tex` into a PDF; this package internally uses a Docker image with TeX Live for compilation. Finally, a GitHub release for the tag is created ([actions/create-release](https://github.com/actions/create-release)) and the compiled PDF is uploaded as a release asset ([actions/upload-release-asset](actions/upload-release-asset)).

All successful workflows can be found in the [Actions](https://github.com/chrissantamaria/resume/actions) tab on GitHub, and builds can be found in the [Releases](https://github.com/chrissantamaria/resume/releases) tab.
