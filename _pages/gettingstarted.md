---
title: "NeurodataWithoutBorders: Neurophysiology"
layout: default
excerpt: "NWB:N"
sitemap: false
permalink: /gettingstarted
---


# Getting Started with NWB:N

## I am scientist/developer in a neuroscience lab and want to start using NWB:N

Welcome! For end-users, the main entry point into the world of NWB:N is usually the PyNWB Python API. Have a look
at our  <a href="https://pynwb.readthedocs.io/en/latest/tutorials/index.html"  target="_blank">tutorials</a>
and also see the <a href="{{ site.url }}{{ site.baseurl }}/pynwb">PyNWB : Python Reference API documentation</a>
in general for more details.

For Matlab users, MatNWB also provides a Matlab API for NWB:N 2.  For more details see
MatNWB repository on <a href="https://github.com/NeurodataWithoutBorders/matnwb"  target="_blank">GitHub</a> or on <a href="https://www.mathworks.com/matlabcentral/fileexchange/67741-neurodatawithoutborders-matnwb" target="_blank">FileExchange</a>.

## I am a developer and would like to contribute to NWB:N development

Welcome! Please see our  <a href="{{ site.url }}{{ site.baseurl }}/contributing">Contributing Guidelines</a> and
<a href="{{ site.url }}{{ site.baseurl }}/code_of_conduct">Code of Conduct</a> for further details. Also
have a look out for [good first_issue](https://github.com/NeurodataWithoutBorders/pynwb/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) and
[help wanted](https://github.com/NeurodataWithoutBorders/pynwb/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)
issue tickes on GitHub.

## I want to get an overview of all the aspects of NWB:N

A general overview and pointers to all relevant documents are available as part of the
<a href="{{ site.url }}{{ site.baseurl }}/overview">Project Overview</a> page. For a more broader overview
of the NeurodataWithoutBorders project at large see also the
<a href="https://www.nwb.org/">nwb.org</a> website.

## Code of Conduct

The PyNWB and nwb-schema projects and everyone participating in it are governed by our
<a href="{{ site.url }}{{ site.baseurl }}/code_of_conduct">Code of Conduct</a> guidelines .
By participating, you are expected to uphold this code.

## Reporting Issues and Contributing

For details on how to contribute to PyNWB and nwb-schema projects see
our <a href="{{ site.url }}{{ site.baseurl }}/contributing">Contributing Guidelines</a>

# Documentation

Detailed documentation of the various aspects of the NWB:N project are available here:

* **General Overview (this website)** : [http://nwb-overview.readthedocs.io](http://nwb-overview.readthedocs.io)
* **PyNWB (API):** [http://pynwb.readthedocs.io](http://pynwb.readthedocs.io)
* **MatNWB (API):** [https://github.com/NeurodataWithoutBorders/matnwb](https://github.com/NeurodataWithoutBorders/matnwb)
* **Data Standard Schema:** [http://nwb-schema.readthedocs.io](http://nwb-schema.readthedocs.io)
* **Specification Language:** [http://schema-language.readthedocs.io](http://schema-language.readthedocs.io)
* **Data Storage:** [http://nwb-storage.readthedocs.io](http://nwb-storage.readthedocs.io)
* **Main Project Site** [http://www.nwb.org/nwb-neurophysiology/](http://www.nwb.org/nwb-neurophysiology/)

The documents are also available in PDF and zipped HTML form for print and offline browsing:

* **PDF**:
    * **Specification Language:** [http://readthedocs.org/projects/schema-language/downloads/pdf/latest/](http://readthedocs.org/projects/schema-language/downloads/pdf/latest/)
    * **Data Standard Schema:** [http://readthedocs.org/projects/nwb-schema/downloads/pdf/latest/](http://readthedocs.org/projects/nwb-schema/downloads/pdf/latest/)
    * **Data Storage:** [http://readthedocs.org/projects/nwb-storage/downloads/pdf/latest/](http://readthedocs.org/projects/nwb-storage/downloads/pdf/latest/)
    * **PyNWB (APIs):** [http://readthedocs.org/projects/pynwb/downloads/pdf/latest/](http://readthedocs.org/projects/pynwb/downloads/pdf/latest/)
    * The **General Overview (this website)** and **MatNWB** docs are currently available online only.
* **HTML Zip**:
    * **Specification Language:** [http://readthedocs.org/projects/schema-language/downloads/htmlzip/latest/](http://readthedocs.org/projects/schema-language/downloads/htmlzip/latest/)
    * **Format Specification:** [http://readthedocs.org/projects/nwb-schema/downloads/htmlzip/latest/](http://readthedocs.org/projects/nwb-schema/downloads/htmlzip/latest/)
    * **Data Storage:** [http://readthedocs.org/projects/nwb-storage/downloads/htmlzip/latest/](http://readthedocs.org/projects/nwb-storage/downloads/htmlzip/latest/)
    * **PyNWB (APIs):** [http://readthedocs.org/projects/pynwb/downloads/htmlzip/latest/](http://readthedocs.org/projects/pynwb/downloads/htmlzip/latest/)
    * The **General Overview (this website)** and **MatNWB** docs are currently not available online only.

Sources
-------

The sources for the API, format specification, and all documents are available here:

* **PyNWB (Python Data API):** [https://github.com/NeurodataWithoutBorders/pynwb](https://github.com/NeurodataWithoutBorders/pynwb) .
    * This repository includes all sources of the PyNWB and FORM APIs as well as
      corresponding documentation and test infrastructure.

* **NWB Schema:** [https://github.com/NeurodataWithoutBorders/nwb-schema](https://github.com/NeurodataWithoutBorders/nwb-schema) .
    * The nwb-schema repository includes among others:
        * ``core`` : YAML specification of the NWB core format
        * ``docs/language`` : Sphinx sources for the specification language documention
        * ``docs/format`` : Sphinx sources for the format specification documentation
        * ``docs/storage`` : Sphinx sources for the data storage documention
        * ``docs/utils`` : Python utilities used for generation of the format documentation from the YAML specification.
          This includes convenient helper functions for rendering specification hierarchies and for generating RST docs.

* **MatNWB** [https://github.com/NeurodataWithoutBorders/matnwb](https://github.com/NeurodataWithoutBorders/matnwb
    * This respository includes all sources of the MatNWB Matlab API.
    
* **NWB DocUtils** [https://github.com/NeurodataWithoutBorders/nwb-docutils](https://github.com/NeurodataWithoutBorders/nwb-docutils)
   * This repository includes tools and cli scripts used to generate documentation for NWB:N.


