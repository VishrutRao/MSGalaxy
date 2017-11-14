---
layout: page
title: Cut_Line_Threshold
description: >
  This tool removes or keeps entire lines based on a threshold input.
---

## Table of Contents
{:.no_toc}
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

## Prerequisites
None



## Manual Installation 
The following file(s) is the script placed in the somewhere in `$GALAXY_ROOT/tools/`.
* 'split_by_feature.py'
* 'split_by_feature.xml'
	
Then edit the '$GALAXY_ROOT/config/tool_conf.xml.main' and specify the path the '*.xml' was placed.

~~~
<toolbox>
.
.
.
    <section id="mat_tools" name="materials tools">
      <tool file="split_by_feature.xml" />
    </section>
~~~

* The file tag can also be in a subdirectory

## Running the Tests
Each 'Repository' has a subdirectory labelled 'test-data'. These are the files that are used as inputs to verify the functionality of the particular tool. This can be done manually by reading the README instructions for each repo or done automatically through the Toolshed installation process.


## Flags

~~~
-f, --file

-c, --column

-p, --prefix

-h, --help

~~~

* '-f' specifies a tabular (csv) file input for processing.
* '-c' specifies on which column on which the data is split.
* '--prefix' specifies the prefix of the filename produced.


## Example

~~~
split_by_feature.sh -f ./test-data/test.txt -c 6 --prefix feature
~~~

## Acknowledgements 
* Original Galaxy Team
* To-do - Add Acknowledgements 