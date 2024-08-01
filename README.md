# stylelint-config-fluid

[![License: BSD 3-Clause](https://badgen.net/github/license/fluid-project/stylelint-config-fluid/)](https://github.com/fluid-project/stylelint-config-fluid/blob/main/LICENSE.md)
[![Latest Release](https://badgen.net/github/release/fluid-project/stylelint-config-fluid/)](https://github.com/fluid-project/stylelint-config-fluid/releases/latest/)
[![NPM Package](https://badgen.net/npm/v/stylelint-config-fluid)](https://www.npmjs.com/package/stylelint-config-fluid)

Shareable Stylelint configuration for the Fluid Project.

## Using

To use the stylelint configuration provided by this module, add it as a dev dependency to your project:

```bash
npm install stylelint-config-fluid --save-dev --save-exact
```

Then, add an `extends` property to your `.stylelintrc.json` file.

```json
{
    "extends": "stylelint-config-fluid"
}
```

## Extending or Overriding Configuration

When using the stylelint configuration provided by this module, you may have a case where you'd like to adjust or extend
the configuration. To do this, add any additional configuration to your own `.stylelintrc.json` file, which extends the
one held in this project.

In the following example, we want to change [the indentation rule](https://stylelint.io/user-guide/rules/indentation) to
tabs. The default configuration provided by the model sets the `indentation` rule to `4` (four spaces), so we need to
extend the configuration with a supplementary `indentation` rule which overrides the default.

```json
{
    "extends": "stylelint-config-fluid",
    "rules": {
        "indentation": "tab"
    }
}
```

See the [stylelint user guide](https://stylelint.io/user-guide/configure#extends) for more options.

## Developing

See the [stylelint user guide](https://stylelint.io/user-guide/configure) for full details on configuration techniques.

### Modifying configuration

To modify the stylelint rules provided by this module, update the configuration in the [.stylelintrc.json](.stylelintrc.json)
file. See the [stylelint user guide](https://stylelint.io/user-guide/configure) for configuration options.

### Testing

To test your changes locally, link the package globally on your system.

```bash
# Run from the stylelint-config-fluid directory.
# Depending on your system, you may need to use sudo.
npm link
```

Add your linked module to the package you want to test in.

```bash
# Run in the root directory for the package with which you want to test the configuration.
npm link stylelint-config-fluid
```

Remove the links to clean up the test settings.

```bash
# Run from the stylelint-config-fluid directory.
# Depending on your system, you may need to use sudo.
npm unlink

# Run in the root directory for the package with which you tested the configuration.
npm unlink stylelint-config-fluid

# Run the install again to ensure that all the dependencies are properly installed.
npm install
```

### Releasing

This module uses [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), enforced with [commitlint](https://commitlint.js.org/).
This facilitates releasing new versions of the module. Release pull requests are generated using [Release Please](https://github.com/google-github-actions/release-please-action).

To cut a release, review and merge the release pull request. This will tag an appropriate [semantic version](https://semver.org)
based on the nature of the recent commits to the project and update [the changelog](CHANGELOG.md).

You will then need to publish the updated version to the [npm registry](http://npmjs.com). This requires an npm account
with appropriate maintainer permissions. To publish the module, run:

```bash
npm publish
```

For more information on publishing to npm, see the [npm publish documentation](https://docs.npmjs.com/cli/publish).
