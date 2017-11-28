---
layout: page
title: Stress Strain Annotation 
description: >
  This detects the features that are present in a single stress strain curve and annotates the document.
---

## Table of Contents
{:.no_toc}
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

<html>
<body>

<iframe width="620" height="445" src="https://www.youtube.com/watch?v=3aVNAIIJ8sg">
</iframe>

</body>
</html>


## Prerequisites
* Python3.5
	* csv
	* os
	* numpy
	* argparse
	* matplotlib
	* sys
	* shutil
	* sklearn 



## Manual Installation 
The following file(s) is the script placed in the somewhere in `$GALAXY_ROOT/tools/`.
* 'stress_strain_characteristic_annotation.py'
* 'stress_strain_characteristic_annotation.xml'
	
Then edit the '$GALAXY_ROOT/config/tool_conf.xml.main' and specify the path the '*.xml' was placed.

~~~
<toolbox>
.
.
.
    <section id="mat_tools" name="materials tools">
      <tool file="stress_strain_feature_annotation.xml" />
    </section>
~~~

* The file tag can also be in a subdirectory

## Running the Tests
Each 'Repository' has a subdirectory labelled 'test-data'. These are the files that are used as inputs to verify the functionality of the particular tool. This can be done manually by reading the README instructions for each repo or done automatically through the Toolshed installation process.


## Flags

~~~
usage: stress_strain_feature_annotation.py [-h] [-f TXT_FILE_PATH]
                                           [-png PNG_FILE_PATH]
                                           [--plot-list PLOT_OPTIONS_LIST]
                                           [--modulus] [--offset]
                                           [--yield-point] [--rupture-point]
                                           [--portional-line] [--plot-all]
                                           [--report REPORT_FILE_PATH]

optional arguments:
  -h, --help            show this help message and exit
  -f TXT_FILE_PATH, --file TXT_FILE_PATH
                        specify the data file location
  -png PNG_FILE_PATH, --png-out PNG_FILE_PATH
                        specify the output png path
  --modulus             plot modulus
  --offset              plot offset
  --yield-point         plot yield point
  --rupture-point       plot rupture point
  --portional-line      plot rupture point
  --plot-all            plot all points point
  --report REPORT_FILE_PATH
                        output a report summary to a file path
~~~

* '-f' specifies a tabular (csv) file input for processing.
* '-png' specifies the file path the png is produced
* '--plot-all' plots all possible features however they can specified individually
	* -modulus
	* -offset
	* -yield-point
	* -rupture-point
	* -portional-line
* '--report' specifies the file path the report is produced



## Example

~~~
stress_strain_feature_annotation.py -f ./test-data/test.txt -png ./out.png --report ./report.txt --plot-all
~~~

## Acknowledgements 
* Original Galaxy Team
* To-do - Add Acknowledgements 