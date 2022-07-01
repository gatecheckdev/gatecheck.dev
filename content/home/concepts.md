---
title: "Concepts"
weight: 3
draft: false
---

## Types

With dozens of popular security and software tools, Gate Check abstracts the terminology.

### Config

The configuration file has the threshold for each artifact.
The Gate Check config (```gatecheck.yaml``` by default) is a customizable collection of tool specific configuration
files.
This file is where the thresholds are set.

### Report

The final report summary that contains the aggregated data used for verification.
```gatecheck-report.json``` by default.
This is a summary of the data collected from the output reports from other tools.

### Artifact

The converted scan output or report from a specific third party tool.
This is the Gate Check internal representation of an output report which is abstracted so it can be output in a
variety of formats.

### Asset

The raw file used to create the artifact or configuration.
Gate Check will bundle all assets and verify the integrity of the files using RSA signing. 