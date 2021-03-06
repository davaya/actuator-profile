# Creating an SBOM Actuator Profile
The OpenC2 [use cases repo](https://github.com/oasis-tcs/openc2-usecases/tree/main/Actuator-Profile-Schemas)
contains a step-by-step guide for creating a device schema from one or more actuator profiles,
along with examples and test data for several devices.  [This repo](https://github.com/davaya/actuator-profile)
is a quick introduction to that process, using the SBOM profile as an example
and defining the JADN schema for an OpenC2 consumer device that performs the SBOM retrieval function.

## 1. Use Case Requirements
The [SBOM AP Repo](https://github.com/oasis-tcs/openc2-ap-sbom) contains an actuator profile template but
no significant profile content.  The issues form the basis for what the profile will need to support,
in particular:
* [Issue #34](https://github.com/oasis-tcs/openc2-ap-sbom/issues/34) - 'List Available SBOMs' and 'Return an SBOM' queries
* 

## 2. JADN Tools
### 2.1 Make Artifacts

The [make-artifacts.py](make-artifacts.py) script translates JADN schemas to multiple formats.
It first creates an *Out* directory if it doesn't exist, then reads each JADN schema
in the Schemas directory and translate it to other formats in the Out directory. The output formats to be
generated can be adjusted by editing the script. The Out directory and its contents can be deleted at any
time, since it will be re-created by any script that creates output files in it.

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
6) [GraphViz](https://graphviz.org/) (schema diagram in dot format, displayable at several locations including [SketchViz](https://sketchviz.com))
7) [PlantUML](http://www.plantuml.com/) (schema diagram in PlantUML format)
8) [JSON Schema]() (schema language for validating JSON data)

Additional output formats can be supported. Because [GraphQL](https://graphql.org/) is under consideration
as a [PACE](https://github.com/opencybersecurityalliance/PACE) interface,
a [GraphQL Schema](https://graphql.org/learn/schema/) translator is being developed.

### 2.2 Resolve Schemas
![resolver](Images/resolver.png)

### 2.3 Test Commands