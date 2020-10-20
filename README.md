# stylelint-config-fluid

[![License](https://badgen.net/github/license/fluid-project/stylelint-config-fluid/)](https://github.com/fluid-project/stylelint-config-fluid/blob/main/LICENSE.md)
[![Latest Release](https://badgen.net/github/release/fluid-project/stylelint-config-fluid/)](https://github.com/fluid-project/stylelint-config-fluid/releases/latest/)
![NPM](https://badgen.net/npm/v/stylelint-config-fluid)


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

When using the stylelint configuration provided by this module, you may have a case where you'd like to adjust or extend the configuration. To do this, add any additional configuration to your own `.stylelintrc.json` file, which extends the one held in this project.

In the following example, we want to change [the indentation rule](https://stylelint.io/user-guide/rules/indentation) to tabs. The default configuration provided by the model sets the `indentation` rule to `4` (four spaces), so we need to extend the configuration with a supplementary `indentation` rule which overrides the default.

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

To modify the stylelint rules provided by this module, update the configuration in the [].stylelintrc.json](.stylelintrc.json) file. See the [stylelint user guide](https://stylelint.io/user-guide/configure) for configuration options.

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
