# Javadoc-publisher.yml
[![Public workflows that use this action.](https://img.shields.io/endpoint?url=https%3A%2F%2Fapi-endbug.vercel.app%2Fapi%2Fgithub-actions%2Fused-by%3Faction%3DMathieuSoysal%2FJavadoc-publisher.yml%26badge%3Dtrue)](https://github.com/search?o=desc&q=MathieuSoysal+javadoc-publisher+path%3A.github%2Fworkflows+language%3AYAML&s=&type=code) [![Test Actions](https://github.com/MathieuSoysal/Javadoc-publisher.yml/actions/workflows/test-action.yml/badge.svg)](https://github.com/MathieuSoysal/Javadoc-publisher.yml/actions/workflows/test-action.yml)*(Tested on Java 8, 11, 17, 19 Maven, Gradle, Ubuntu, Macos, windows)*


Automatically generate Javadoc from your maven project and deploy it with GitHub Page on *javadoc* branch.

## Requirements
- Your project need to use **Maven** or **Gradle**.

## Usage

### For Maven project

The workflow, usually declared in `.github/workflows/javadoc-publish.yml`, looks like:

<details open>

<summary>.github/workflows/publish-javadoc-maven.yml</summary>

```YAML
name: Deploy Javadoc

on:
  push:
    branches:
      - master
      - main

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - name: Deploy JavaDoc 🚀
        uses: MathieuSoysal/Javadoc-publisher.yml@v2.0.4
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          javadoc-branch: javadoc
          java-version: 17
          target-folder: javadoc 
```
</details>

### For Gradle project

The workflow, usually declared in `.github/workflows/javadoc-publish.yml`, looks like:

<details open>
<summary>.github/workflows/publish-javadoc-gradle.yml</summary>



```YAML
name: Deploy Javadoc

on:
  push:
    branches:
      - master
      - main

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - name: Deploy JavaDoc 🚀
        uses: MathieuSoysal/Javadoc-publisher.yml@v2.0.4
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          javadoc-branch: javadoc
          java-version: 17
          target-folder: javadoc 
          project: gradle
```
</details>

### GitHub page

Don't forget to configure your repository settings with your new GitHub Page. 😉

### Badge

```Markdown
[![Javadoc](https://img.shields.io/badge/JavaDoc-Online-green)](https://YOUR-USERNAME.github.io/YOUR-REPO/javadoc/)
```
In the badge link, replace *YOUR-USERNAME* with your GitHub Username and replace *YOUR-REPO* with the name of your GitHub repository.

## License
The Dockerfile and associated scripts and documentation in this project are released under the [Apache 2.0 License](https://github.com/MathieuSoysal/Javadoc-publisher.yml/blob/main/LICENSE).
