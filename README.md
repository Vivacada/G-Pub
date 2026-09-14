# G-Pub

## 1 - Abstract

***Publish and Prosper***

G-Pub is a repository format for academic and academia-adjacent publishing.

In a G-Pub repo, the root folder will have a single README file, holding the main publication of
the repo. It should be written in a plain text format, and ideally accompanied by a "LICENSE.md"
file. There may also be a "JPUB.json" file, written in the G-Pub JSON file format, and containing
all citations. Some G-Pub repos may omit the README paper and have only the G-Pub JSON file.

Any other assets in the repo will be treated as assets, but ideally, they should all be nested in a
folder called "Assets".

## 2 - Contents

### 2.1 - Formats

#### 2.1.1 - G-Pub JSON

The G-Pub JSON format consists of a JSON list of G-Pub objects, each of which represents a
reference to another resource.

A G-Pub object shall have a "source" field, containing a string or string list, containing links to
the referenced resource, the order of which in the case of a list may inform source priority.

Additionally, a G-Pub object may have a "properties" object, and below is a table of the various
fields said properties object may have.

| Name | Type | Details |
| --- | --- | --- |
| "name" | String | Resource name |
| "date" | String Date-Time | When the reference was added to the repo. |
| "origin" | Number List (Size 2) | Beginning and Ending indices of referencing substring |
| "target" | Number List (Size 2) | Beginning and Ending indices of referenced substring |
| "notes" | String or String List | Arbitrary Comments |
| "verify" | Boolean | True to approve resource; False to disapprove resource |

The order of the objects in the root list may be used to inform proper reading order.

#### 2.1.2 - G-Pub Document

The G-Pub document format divides an academic-style document into a title, an abstract, and a
contents section, the latter of which may have indefinite nested subsections, numbered accordingly,
as demonstrated in this document which itself is in said format.

### 2.2 - Conventions

#### 2.2.1 - Trust Model

The G-Pub standard trust model (STM) has a given party select a set of G-Pub repos they trust, and
judges the trustworthiness of directly and indirectly referenced repos by degree of separation to
the manually selected trusted repos and by the number of positive, neutral, and negative references
received relative to the trustworthiness of the repos that granted said references.