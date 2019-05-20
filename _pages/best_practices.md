# Best Practices

The following document is a summary of a meeting of NWB:N developers, contributors and early adopters at the 
Hackathon #6 at HHMI Janelia Research Campus on May 16th, 2019.

### Authors
Oliver Ruebel, Andrew Tritt, Ryan Ly, Benjamin Dichter, ...


## Preamble
NWB:N has a high degree of flexibility that allows it to accommodate the needs of the diverse neuroscience community; 
however this can create a challenge. New users struggle because they have a number of different ways they can put data
into this format and they do not know which way is best. Tool builders also struggle with this flexibility because they 
prefer to have a more predictable structure to build analysis tools against. We could address this by imposing stricter
rules in the NWB:N standard, but this would break backwards compatibility and might hinder the format's flexibility.
Here, we strike a compromise, by describing "best practices." This is a document of advise from developers and
experienced users that outlines some of the pitfalls to avoid and usage patterns to emulate so that you can fully
leverage the tools in the NWB:N ecosystem.

## NWB Files
An `NWBFile` object generally contains data from a single experimental session.

### identifiers


## DynamicTables
### bools
Although boolean values (`True`/`False`) are not used in the core schema, they are a supported data type, and we
encourage the use of `DynamicTable` columns with boolean values. For instance, boolean values would be appropriate for
a `correct` custom column to the trials table.

### times
In `TimeInterval` objects such as the trials and epochs table, `start_time` and `stop_time` should both be in seconds 
with respect to the `session_start_time` (as are all times in  NWB:N). If you add more times in the trials 
table, for instance a subject response time, name it with `_time` at the end (e.g. `response_time`) and store the time
values in seconds from the `session_start_time`, just like `start_time` and `stop_time`.

### electrodes: 'location'
The `'location'` column of the electrodes table is meant to store the brain region that the electrode as in. Different
labs have different standards for electrode localization. Some use atlases and coordinate maps to precisely place an
electrode, and use physiological measures to confirm its placement. Others use histology or imaging processing 
algorithms to identify regions after-the-fact. You fill this column with localization results from your most accurate
method. For instance, if you target electrodes using physiology, and later use histology to confirm placement, we would
recommend that you add a new column to the electrodes table called `'location_target'`, set those values to the original
intended target, and alter the values of `'location'` to match the histology results.

It is preferable to use established ontologies instead of lab conventions for indicating anatomical region. We recommend
the Allen Brain Atlas terms for mice, and you may use either the full name or the abbreviation (do not make up your own
terms.)

The location column of the electrodes table is required. If you do not know the location of an electrode, use `'unknown'`.

## Naming of neurodata_types
Many of the neurodata_types in NWB:N have a flexible name. This allows multiple objects of the same type to be stored
side-by-side and allows data writers to provide human-readable information about the contents of the neurodata_type. If 
appropriate, simply use the name of the neurodata_type as the name of that object. For instance, if you are
placing an `ElectricalSeries` object in `/acquisition` that holds voltage traces for a multichannel recording, consider
simply naming that object `"ElectricalSeries"`. This is the default_name for that object, and naming it this will increase
your chances that analysis and visualization tools will operate seamlessly with you data.

If you need to place other data of the same neurodata_type, you will need to choose another name. Keep in mind that
meta-data should not be stored solely in the name of objects. It is OK to name an object something like 
"ElectricalSeries_large_array" however the name alone is not sufficient documentation. In this case, the source of the
signal will be clear from the device of the rows from the linked electrodes table region, and you should also include
any important distinguishing information in the `description` field of the object. Make an effort to make meta-data as
explicit as possible. Good names help users but do not help applications parse your file.

When creating a custom name, do not use the forward slash (`/`), as this can confuse `h5py` and create an additional
group. For instance, the `DfOverF` group should not be stored with the name `df/f`. For this and similar cases use 
"`Over`" like in `DfOverF`.

### Naming of processing modules
In NWB:N version [ver], optional processing modules will be added to increase standardization of processing module names.
These names mirror the extension module names: "ecephys", "icephys", "behavior", "ophys", "misc". If appropriate, we
encourage the use of these defaults. There may be some cases when deviating from this pattern is appropriate. For
instance, if there is a processing step that involves data from multiple modalities, or if the user wants to compare two
processing pipelines for a single modality (e.g. different spike sorters). In cases like these, you may create 
`ProcessingModules` with custom names. `ProcessingModules` are themselves neurodata_types, and the other rules for
neurodata_types also apply here.


## Unit (of measurement)
Every `TimeSeries` instance has a `unit` as an attribute of the `data` Dataset, which is meant to indicate the unit of
measurement of that data. We advise using SI units. Time is always in units of seconds.


## Simulated data
You may store the result of simulations in NWB files. In this case, the goal is to store data as if it were recorded
**in vivo** to facilitate comparison between simulated results and **in vivo** results. Core components of the NWB:N
schema and HDF5 backend have been engineered to handle data from hundreds of thousands of units, and natively support 
parallel data access via MPI, so much of the NWB:N format should work for large-scale simulations out-of-the-box. The
neurodata extension "simulation_output" provides a neurodata_type for storing continuous recordings from multiple cells
and multiple compartments per cell. The extension only supports storing the output data of a simulation and does not 
support parameters for simulation configuration. This is out-of-scope for NWB:N, since it does not facilitate
side-by-side comparison between stimulated and **in vivo** results, and is quite difficult to generalize given the
diversity of ways one can parametrize a simulation. That said, if you would benefit from storing such data in your 
NWB:N file, you might consider creating your own custom extension.
