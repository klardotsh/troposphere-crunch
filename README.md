# troposphere-crunch
A tool to compile and (optionally) deploy Troposphere templates with AWS CLI and
a very opinionated structure.

> 21 Sept 2020: This is not, and has not for quite some time been, maintained,
> mostly because I never really ended up using it to begin with. Fork it and do
> whatever with it. The license was previously MIT, but it has now been changed
> to Creative Commons Zero. Enjoy!

## Installation

Install through pip/pipenv/poetry/whatever as usual. It's [on
PyPi](https://pypi.org/project/troposphere_crunch/).

## Usage

You'll need a `stacks.toml` file that defines the following:

- `module`, an importable Python module path (relative to current working
  directory or otherwise within your `PYTHONPATH`) which contains a variable
  `template`, which is a Troposphere `Template` instance.

- `capabilities` (optional): a list of `awscli` capabilities, ex.
  `['CAPABILITY_IAM', 'CAPABILITY_NAMED_IAM']`

- `region` (optional, default=`us-west-2`): `awscli`-compatible region string

- `output_dir` (optional, default=`cloudformation`): output directory for the
  compiled JSON templates

You'll use this file as `CONFIG`. From here, refer to the `--help` output:

```
usage: troposphere-crunch [-h] -c CONFIG [-C] [-d] [-o OUTPUT_DIR]

A tool to compile and (optionally) deploy Troposphere templates with AWS CLI
and a very opinionated structure

optional arguments:
  -h, --help            show this help message and exit
  -c CONFIG, --config CONFIG
                        path to TOML config file
  -C, --clean           remove output_dir before building templates
  -d, --deploy          after building, actually deploy stacks with awscli
  -o OUTPUT_DIR, --output-dir OUTPUT_DIR
                        default output directory (overridable per stack in
                        config)
```

## License

[Creative Commons CC0 1.0
Universal](https://creativecommons.org/publicdomain/zero/1.0/), summarized
below:

>The person who associated a work with this deed has dedicated the work to the
public domain by waiving all of his or her rights to the work worldwide under
copyright law, including all related and neighboring rights, to the extent
allowed by law.
>
>You can copy, modify, distribute and perform the work, even for commercial
purposes, all without asking permission. See Other Information below.
>
> **Other Information**
>
> - In no way are the patent or trademark rights of any person affected by CC0,
>   nor are the rights that other persons may have in the work or in how the
>   work is used, such as publicity or privacy rights.
>
> - Unless expressly stated otherwise, the person who associated a work with
>   this deed makes no warranties about the work, and disclaims liability for
>   all uses of the work, to the fullest extent permitted by applicable law.
>
> - When using or citing the work, you should not imply endorsement by the
>   author or the affirmer.
