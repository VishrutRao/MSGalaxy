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

<html>
<body>

<iframe width="420" height="315" src="https://www.youtube.com/watch?v=3aVNAIIJ8sg">
</iframe>

</body>
</html>


## Prerequisites
* Python2.7
	* re
	* os
	* sys
	* argparse
	* math


## Manual Installation 
The following file(s) is the script placed in the somewhere in `$GALAXY_ROOT/tools/`.
* 'stress_strain_cycle_annotation.py'
* 'stress_strain_cycle_annotation.xml'
	
Then edit the '$GALAXY_ROOT/config/tool_conf.xml.main' and specify the path the '*.xml' was placed.

~~~
<toolbox>
.
.
.
    <section id="mat_tools" name="materials tools">
      <tool file="stress_strain_cycle_annotation.xml" />
    </section>
~~~

* The file tag can also be in a subdirectory

## Running the Tests
Each 'Repository' has a subdirectory labelled 'test-data'. These are the files that are used as inputs to verify the functionality of the particular tool. This can be done manually by reading the README instructions for each repo or done automatically through the Toolshed installation process.

## Example

~~~
stress_strain_cycle_annotation.py -f ./test-data/test.txt
~~~

## Acknowledgements 
* Original Galaxy Team
* To-do - Add Acknowledgements 