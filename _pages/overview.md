---
title: "NeurodataWithoutBorders: Neurophysiology"
layout: default
excerpt: "NWB:N"
sitemap: false
permalink: /overview
---


# NWB:N Overview

<img alt="NWB:N Components" src="images/project_components.png" width="600" class="center-block">


The following provides a high-level overview of the main components for the NWB:N data standardization 
ecosystem. For each component we provide an overview of the problem, its function and a description.


### Data API(s)

**Problem:** Efficient interaction with neuroscience data

**Approach:** Develop APIs that provide easy-to-use representations of NWB:N neurodata 
types for programmatic use and enable the mapping of these representations to/from data 
storage based on the NWB:N format specification.

**Function:** The role of data API(s) is to facilitate efficient interaction 
with neuroscience data stored in the NWB:N data format (e.g,. for reading, 
writing, querying, and analyzing neuroscience data). An API provides a stable 
and usable interface for programmatic use and development of new applications. 
The API should insulate developers and users from implementation details related 
to the specification language, format specification, and data storage.

**Description** NWB:N currently provides the following APIs

* **PyNWB:** PyNWB provides critical functionality needed to read, write, use, extend, 
  and analyze data stored in NWB:N using the Python programming language. 
  PyNWB is the reference API for NWB:N 2.

   * <a href="{{ site.url }}{{ site.baseurl }}/pynwb">Documentation</a>
   * <a href="https://github.com/NeurodataWithoutBorders/pynwb"  target="_blank">Sources (GitHub) </a>


* **MatNWB:** MatNWB is a Matlab API for NWB:N. MatNWB generates Matlab classes
  for representing NWB:N neurodata_types directly from the YAML specification. 
  The sources for MatNWB are available on
  <a href="https://github.com/NeurodataWithoutBorders/matnwb" target="_blank">GitHub</a>


### Specification Language

**Problem:** Definition of neuroscience data standards.

**Approach:** To support the formal and verifiable specification of neurodata 
file formats, NWB:N relies on the NWB:N specification language.

**Function:** The specification language provides mechanism to formally specify the organization of data.

**Description:** The specification language is defined in YAML (or JSON). The specification 
language defines formal structures for describing the organization of complex data using 
basic concepts, e.g., Groups, Datasets, Attributes, and Links. The specification language 
is used to extend the format, which is necessary to store types of data that are not 
currently managed by the format

*  <a href="{{ site.url }}{{ site.baseurl }}/schemalanguage"> Specification Language Documentation</a>

### Data Standard Schema

**Problem:** Organization of complex collections of neuroscience data.

**Approach:** Organize data hierarchically using easy-to-use primitives, e.g., Groups 
(similar to Folders), Datasets (n-D Arrays), Attributes (Metadata objects on Groups 
and Datasets), and Links (links to Groups and Datasets).

**Function:** The format specification formally specifies the organization of 
neuroscience data. The format specification provides a verifiable, computer and 
human readable document that governs the NWB:N format. The format specification 
is, hence, central to support development of API’s and codes compliant with 
the NWB format and extension of the NWB format.

**Description:** The NWB:N format standard is governed by a formal format specification, 
the NWB:N schema that is formally specified using the NWB specification language. A 
new schema file will be published for each revision of the NWB format standard. 
Developers can use the schema to validate NWB files or create advanced APIs for NWB data.

* <a href="{{ site.url }}{{ site.baseurl }}/datastandard">Data Standard Schema Documentation</a>
* <a href="https://github.com/NeurodataWithoutBorders/nwb-schema" target="_blank">Sources (GitHub)</a>


### Data Storage

**Problem:** Storage of large collections of neuroscience data.

**Approach:** The NWB:N format currently uses the [Hierarchical Data Format (HDF5)](https://portal.hdfgroup.org/display/HDF5/HDF5)
as primary storage mechanism.

**Function:** Data storage maps NWB:N primitives (Groups, Datasets, Attributes, Links etc.) 
to storage. In the case of HDF5 this is currently mostly a 1-to-1 mapping as 
the NWB:N primitives largely match HDF5 primitives.

**Description:** HDF5 was selected for the NWB:N format because it meets several key 
requirements. First, HDF5 it is a mature data format standard with libraries available 
in multiple programming languages. Second, HDF5’s hierarchical structure allows data 
to be grouped into logical self-documenting sections. The HDF5 structure is analogous 
to a file system in which its “groups” and “datasets” correspond to directories and files. 
Groups and datasets can have attributes that provide additional details, such as 
authorities’ identifiers. Third, the HDF5 linking feature enables data stored in one 
location to be transparently accessed from multiple locations in the hierarchy. The 
linked data can be external to the file. Fourth, HDF5 is widely supported across 
programming languages (e.g., C, C++, Python, MATLAB, R among others) and tools, 
such as, [HDFView](https://portal.hdfgroup.org/display/HDFVIEW/HDFView), a free, 
cross-platform application, can be used to open a file and browse data. Fifth, 
the HDF Group, a nonprofit group, ensures the ongoing accessibility of 
HDF-stored data.

*  <a href="{{ site.url }}{{ site.baseurl }}/storage_hdf">Data Storage Documentation</a>








