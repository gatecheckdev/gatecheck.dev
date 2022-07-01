---
title: "Getting Started"
weight: 2
draft: false
---

The fastest way to get started with Gate Check is to download the pre-built binaries for your target system.

```shell
cd <target install dir>
curl -L <OS Specific Release>.tar.gz | tar xz
./gatecheck
./gatecheck --help
```

Gate Check uses Cobra for the CLI, so the normal convention of using ```--help``` to see command usage works.

To generate a configuration file with the default thresholds set

```shell
gatecheck config init .
cat gatecheck.yaml
```

Add a grype report

```shell
gatecheck report add grype grype-report.json
gatecheck report print
```

**Note** You can specify specific config files or report files with ```--config FILE``` and/or ```--report FILE```
respectively.
Without the flags, it will look for ```gatecheck.yaml``` and ```gatecheck-report.json``` in the working directory

Add additional information to a report
```shell
gatecheck report update --report gatecheck-report.json --url "gitlab.com/piplineid" --id "abc-12345"
gatecheck report print --report gatecheck-report.json
```

If you want to apply a modified configuration file to the report, it can be done like so:
```shell
gatecheck report update --report gatecheck-report.json --config custom-config.yaml
gatecheck report print --report gatecheck-report.json
```
