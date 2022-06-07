# Standards

## Style Guide

The Growr Community provides a set of guidelines for the style of code we write. These standards help ensure that the Growr codebase remains high quality, maintainable and consistent.

The goal of these guides is to ensure an easy developer workflow and reduce code commits that contain changes for the sake of style over content. By reducing the noise in diffs we make the job of reviewers easier. 

### Code Style

#### Javascript

Growr uses the Javascript code style dictated by [StandardJS](https://standardjs.com/). For a full set of rules, refer to the [Standard Rules](https://standardjs.com/rules.html), but as a brief set of highlights:

- Use *2 spaces* for indentation

```js
function helloWorld (name) {
  console.log('hi', name)
}
```

- Use *single quotes* for strings except to avoid escaping.

```js
console.log('hello there')    // ✓ ok
console.log("hello there")    // ✗ avoid
console.log(`hello there`)    // ✗ avoid
```

- No semicolons. (see: 1, 2, 3)

```js
window.alert('hi')   // ✓ ok
window.alert('hi');  // ✗ avoid
```

#### YAML

While YAML deserializers can vary from one to another, we follow the following rules when writing YAML:
> Credit: these examples were taken from the [flathub style guide](https://github.com/flathub/flathub/wiki/YAML-Style-Guide)

- 2 space indents
- Always indent child elements

```yaml
# GOOD:
modules:
  - name: foo
    sources:
      - type: bar

# BAD:
modules:
- name: foo
  sources:
  - type: bar
```

- Do not align values

```yaml
# BAD:
id:           org.example.Foo   
modules:
  - name:     foo
    sources:
      - type: git
```
#### sh + bash

- The Shebang should respect the user's local environment:

```bash
#!/usr/bin/env bash
```

This ensures that the script will match the `bash` that is defined in the user's environment, instead of hardcoding to a specific bash at `/usr/bin/bash`. 

- When referring to other files, don't use relative paths:

This is because your script will likely break if somebody runs it from a different directory from where the script is located

```bash
# BAD:
cat ../Dockerfile | wc -l

# GOOD:
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
cat ${DIR}/../Dockerfile | wc -l 
```

For recommended bash conventions, refer to this blog post: [Best Practices for Writing Shell Scripts](https://kvz.io/bash-best-practices.html)

### Documentation

Documentation should be written in Mark Down format.  

### Directory Structure

....

### Design + Implementation Guidelines

These guidelines are meant as recommendations for writing code in the Growr community (or code that will be adopted into the community). If you are writing code that you wish to donate code to the community, we ask that you follow these guidelines as much as possible to aid with the consistency and maintainability of the codebase. Donations that adhere to these guidelines will be adopted more easily and swiftly.

#### Tools + Frameworks

In the Growr Community, we are prefer the following tools and frameworks:

- **Microservice framework:** [`MoleculerJS`](https://github.com/moleculerjs/moleculer)
  - **API** GraphQL using MoleculerJS modules
- **Web UI Framework:** [`ReactJS`](https://reactjs.org/)
- **Package Management:** `npm`
- **Containers and Orchestration:** [`docker`](https://www.docker.com/) and [`kubernetes`](https://kubernetes.io/)
- **Unit Testing:** [`Jest`](https://jestjs.io/) for new codebases.
- **CI:** 

By using these tools and frameworks, we maintain a high level of consistency and maintainability across the codebase, which keeps our developers productive and happy. While we don't mandate that donated codebases use these same tools and frameworks, we would like to stress that adoptions that use different tools could create an undue maintenance burden on the Community.

### Adopting Open Source Contributions into Growr

#### Step 0: Prerequisites

### Versioning

[Semantic versioning 2.0.0](https://semver.org/) is used across the Growr services. 

### Creating new Features

Process for creating new [features and branches](creating-new-features.md) in Growr.

### Pull Request Process

Submit pull requests which include both the change and the reason for the change. Feel free to use GitHub's "Draft Pull Request" feature to open up your changes for comments and review from the community.

### Code of conduct 

We use the [Growr Code of Conduct](./code-of-conduct.md)

### Licensing

See [License](https://github.com/mojaloop/mojaloop/blob/master/contribute/License.md) policy