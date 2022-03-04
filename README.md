# Creating an Actuator Profile
The OpenC2 [use cases repo](https://github.com/oasis-tcs/openc2-usecases/tree/main/Actuator-Profile-Schemas)
contains a step-by-step guide for creating a device schema from one or more actuator profiles,
along with examples and test data for several devices.

[This repo](https://github.com/davaya/actuator-profile) is intended to be a quick introduction to that
process, focusing on a single-profile device and background on JADN and schema-based development.

### Use Cases

### JADN Tools

The [make-artifacts.py](make-artifacts.py) script
will create an Out directory if it doesn't exist, then read each JADN schema
in the Schemas directory and translate it to other formats in the Out directory. The output formats to be
generated can be adjusted by editing the script.

**Input Formats**

1) [Normative JADN]() (JSON data)
2) JADN [interface definition language]() (IDL - a plain text format)
3) HTML tables (must have been created by the translator to include field tags)

**Output Formats**

1) Normative JADN (pretty-printed JSON data)
2) Normative JADN core (JSON data with all [extensions]() converted to core types and comments stripped)
3) JADN IDL
4) HTML tables
5) [Markdown tables]() as used in OpenC2 documents
6) [GraphViz]() (schema diagram in dot format)
7) [PlantUML]() (schema diagram in PlantUML format)
8) [JSON Schema]() (schema language for validating JSON data)

Additional output formats can be developed. Because [GraphQL](https://graphql.org/) is under consideration
as a [PACE](https://github.com/opencybersecurityalliance/PACE) interface,
a [GraphQL Schema](https://graphql.org/learn/schema/) translator is being developed.