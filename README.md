# Resume

LaTeX source for my personal resume linked on [my site](https://chris.santamaria.me/), based on an awesome template found [here](https://github.com/lcfyi/software-resume-template). Uses a GitHub Actions workflow for automatic PDF builds uploaded as releases.

## Actions Workflow

The action is triggered on a version tag push. To tag changes and push with a tag to GitHub:

```bash
# create a new tag
git tag v1.0.0
# push code
git push
# push tags
git push --tags
```

The repository is first cloned using [actions/checkout](https://github.com/actions/checkout). Next, [latex-action](https://github.com/xu-cheng/latex-action) is triggered to compile `resume.tex` to a PDF; this package internally uses a Docker image with TeX Live for building. Finally, a GitHub release for the tag is created ([actions/create-release](https://github.com/actions/create-release)) and the built PDF is uploaded as a release asset ([actions/upload-release-asset](actions/upload-release-asset)).

All successful workflows can be found in the [Actions](https://github.com/chrissantamaria/resume/actions) tab on GitHub, and builds can be found in the [Releases](https://github.com/chrissantamaria/resume/releases) tab.
