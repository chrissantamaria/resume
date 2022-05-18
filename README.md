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

GitHub Actions then:

- clones the repo with [actions/checkout](https://github.com/actions/checkout)
- compiles `resume.tex` to a PDF with [latex-action](https://github.com/xu-cheng/latex-action) (this package internally uses a Docker image with TeX Live for building)
- creates a GitHub release for the tag with [actions/create-release](https://github.com/actions/create-release)
- uploads the built PDF as a release asset with [actions/upload-release-asset](actions/upload-release-asset)

All successful workflows can be found in the [Actions](https://github.com/chrissantamaria/resume/actions) tab on GitHub, and builds can be found in the [Releases](https://github.com/chrissantamaria/resume/releases) tab.
