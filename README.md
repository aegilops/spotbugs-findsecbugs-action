# spotbugs-findsecbugs-action

🚨 This repo has moved to [advanced-security/spotbugs-findsecbugs-action](https://github.com/advanced-security/spotbugs-findsecbugs-action/) 🚨

> ℹ️ This is an _unofficial_ tool created by Field Security Services, and is not officially supported by GitHub.

This Action run SpotBugs with FindSecBugs, and uploads the results to GitHub Code Scanning.

Set up a workflow that builds your JVM language project, then run this Action on the resulting build artifacts (JARs, WARs, class files, etc.).

## Usage

First, build your Java, Scala or other JVM language project in an Actions workflow.

Then, set up this Action as a step in your Actions workflow, e.g. for a typical Scala project:

```yaml
    - name: Run SpotBugs with FindSecBugs
      uses: advanced-security/spotbugs-findsecbugs-action@v1
      with:
        spotbugs_target: 'target/scala-*/classes'
```

## Inputs

* `spotbugs_version`: The version of SpotBugs to use. Default: `4.7.3`
* `findsecbugs_version`: The version of FindSecBugs to use. Default: `1.12.0`
* `spotbugs_target`: The target to run SpotBugs against. Default: `*.jar`
* `upload_sarif`: Whether to upload the SARIF file to GitHub Code Scanning. Default: `true`
* `java_distribution`: The Java distribution to use. Default: `microsoft`
* `java_version`: The Java version to use. Default: `11`
* `no_cache`: Do not use cached versions of the Spotbugs and FindSecBugs tools. Default: `false`

## Full sample workflow

See [starter-workflow.yml](starter-workflow.yml) for a full sample workflow.

## Q&A

Q: Why is this Action needed?
A: Several SpotBugs plugins are usable in CI/CD and Actions, but don't output SARIF, and they're not available for all JVM languages and build systems.

Q: Why doesn't the Action support setting argument X of SpotBugs?
A: It's a work-in-progress. Please raise an issue or a PR if you need a feature.

## Requirements

* GitHub Actions runner

## License

This project is licensed under the terms of the MIT open source license. Please refer to the [LICENSE](LICENSE) for the full terms.

## Maintainers

See [CODEOWNERS](CODEOWNERS) for the list of maintainers.

## Support

> ℹ️ This is an _unofficial_ tool created by Field Security Services, and is not officially supported by GitHub.

See the [SUPPORT](SUPPORT.md) file.

## Background

See the [CHANGELOG](CHANGELOG.md), [CONTRIBUTING](CONTRIBUTING.md), [SECURITY](SECURITY.md), [SUPPORT](SUPPORT.md), [CODE OF CONDUCT](CODE_OF_CONDUCT.md) and [PRIVACY](PRIVACY.md) files for more information.
