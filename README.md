# Quarto Extension `simple-vars`

[Quarto][] supports the handy idea of [variables][].

In a Quarto project, the `var` shortcode enables you to insert content from a project-level `_variables.yml` file where you can keep commonly used text such as nicely formatted website links, etc. For example, if that file contains the line:

```yml
quarto: [`Quarto`](https://quarto.org)
```

Then, in markup, you can reference the `quarto` variable as follows:

```qmd
The project's documentation site was built using {{< var quarto >}}.
```

This will be rendered as:

> The project's documentation site was built using [`Quarto`](https://quarto.org).

That is all well, but I find the Quarto shortcode syntax `{{< var variable-name >}}` to be pretty clunky. By contrast, [AsciiDoc][] uses the much simpler `{variable-name}` to achieve the same effect.

This `simple-vars` extension for Quarto lets you use the AsciiDoc approach to reference the variables defined in the `_variables.yml` file. That earlier example becomes:

```qmd
The project's documentation site was built using {quarto}.
```

It eliminates the need for all the extra braces, etc. Your markup is cleaner, but you still get the same output:

> The project's documentation site was built using [`Quarto`](https://quarto.org).

## Installing

The command

```bash
quarto add nessan/simple-vars
```

installs the extension under the `extensions` subdirectory, which should be checked in if you use version control.
Once it is installed, you add the extension as a filter in your `_quarto.yml` file as usual

```yml
filters:
    - simple-vars
```

## Example

See the `examples` directory for demonstration projects using this extension.

## Contact

You can contact me by email [here](mailto:nzznfitz+gh@icloud.com).

## Copyright and License

Copyright (c) 2024-present Nessan Fitzmaurice.
You can use this software under the [MIT license][].

<!-- Reference links -->

[Quarto]: https://quarto.org
[variables]: https://quarto.org/docs/authoring/variables.html
[AsciiDoc]: https://asciidoc.org
[MIT license]: https://opensource.org/license/mit
