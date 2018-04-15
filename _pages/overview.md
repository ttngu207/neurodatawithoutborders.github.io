---
title: "NeurodataWithoutBorders: Neurophysiology"
layout: default
excerpt: "NWB:N"
sitemap: false
permalink: /overview
---


# NWB:N Overview

<img alt="NWB:N Components" src="images/project_components.png" width="600" class="center-block">


The following provides a high-level overview of the various main components for the NWB:N data standardization
ecosystem. For each component we provide and overview of the problem, approach, description,
and function.

### Data API(s)

**Problem:** How to efficiently interact with neuroscience data?

**Approach:** Develop APIs that provides users easy-to-use representations of
NWB:N neurodata types for programmatic use and enable the mapping of these representations
to/from data storage based on the NWB:N format specification.

**Function:** The role of data API(s) is to facilitate efficient interaction
with neuroscience data stored in the NWB:N data format
(e.g,. for reading, writing, querying, and analyzing neuroscience data).
A main function of an API is provide users a stable and usable interface
for programmatic use and development of new applications. As such, a
central function of the API is also to insulate developers and users from
implementation details regarding the specification language, format specification,
and data storage.

**Description** NeurodataWithoutBorders currently provides the following APIs for NWB:N

* **PyNWB:** PyNWB provides critical functionality needed to read, write, use, and
  analyse data stored in NWB:N. PyNWB provides users an easy-to-use interface and abstractions
  for integrating NWB types with their codes while insulating them from implementation
  details with respect to specification language, format, and storage. PyNWB is the reference
  API for NWB:N 2.

   * <a href="{{ site.url }}{{ site.baseurl }}/pynwb">Documentation</a>
   * <a href="https://github.com/NeurodataWithoutBorders/pynwb"  target="_blank">Sources (GitHub) </a>


* **MatNWB:** MatNWB is a Matlab API for NWB:N. MatNWB generates Matlab classes for
  representing NWB:N *neurodata_types* directly from the YAML specification.
  The sources for MatNWB are available on
  <a href="https://github.com/NeurodataWithoutBorders/matnwb" target="_blank">GitHub</a>


### Specification Language

**Problem:** How to formally define neuroscience data standards?

**Approach:** In order to support the formal and verifiable specification of neurodata
file formats, NWB:N defines and uses the NWB specification
language.

**Function:** The primary function of the specification language is to enable
the formal specification of data organizations.

**Description:** The specification language is
defined in YAML (or JSON). The specification language defines formal
structures for describing the organization of complex data using basic
concepts, e.g., Groups, Datasets, Attributes, and Links.
Data publishers can use the specification language to extend
the format in order to store types of data not managed by the base format.

*  <a href="{{ site.url }}{{ site.baseurl }}/schemalanguage"> Specification Language Documentation</a>

### Data Standard Schema

**Problem:** How to organize complex collections of neuroscience data?

**Approach:** Organize data hierarchically using easy-to-use primitives, e.g.,
Groups (similar to Folders), Datasets (n-D Arrays), Attributes (Metadata objects on Groups and Datasets),
and Links (links to Groups and Datasets).

**Function:** The primary function of the format specification is to formally specify
the NWB format describing the organization of neuroscience data. The format specification
provides a verifiable, computer and human readable document that governs the NWB format.
The format specification is, hence, central to support development of API's and codes
compliant with the NWB format and extension of the NWB format.

**Description:** The NWB format standard is governed by a formal format specification,
the NWB:N schema that is formally specified using the NWB specification language.
A new schema file will be published for each revision of the NWB format
standard. Developers can use the schema to validate NWB files or create
advanced APIs for NWB data.

* <a href="{{ site.url }}{{ site.baseurl }}/datastandard">Data Standard Schema Documentation</a>
* <a href="https://github.com/NeurodataWithoutBorders/nwb-schema" target="_blank">Sources (GitHub)</a>


### Data Storage

**Problem:** How to store large collections of neuroscience data?

**Approach:** NWB:N format currently uses the [Hierarchical Data Format (HDF5)](https://www.hdfgroup.org/HDF5/)
as primary storage mechanism.

**Function:** A primary function of the data storage is to map
NWB:N primitives (Groups, Datasets, Attributes, Links etc.) to storage.
In the case of HDF5 this is currently mostly a 1-to-1 mapping as the NWB:N
primitives largely match HDF5 primitives.

**Description:** HDF5 was selected for the NWB format because it met several of the project's
requirements. First, it is a mature data format standard with libraries
available in multiple programming languages. Second, the format's
hierarchical structure allows data to be grouped into logical
self-documenting sections. Its structure is analogous to a file system
in which its "groups" and "datasets" correspond to directories and
files. Groups and datasets can have attributes that provide additional
details, such as authorities' identifiers. Third, its linking feature
enables data stored in one location to be transparently accessed from
multiple locations in the hierarchy. The linked data can be external to
the file. Fourth, HDF5 is widley supported across programming languages
(e.g., C, C++, Python, MATLAB, R among others) and tools, such as,
[HDFView](https://www.hdfgroup.org/products/java/hdfview/), a free,
cross-platform application, can be used to open a file and browse data.
Finally, ensuring the ongoing accessibility of HDF-stored data is the
mission of The HDF Group, the nonprofit that is the steward of the
technology.

*  <a href="{{ site.url }}{{ site.baseurl }}/storage_hdf">Data Storage Documentation</a>








