---
layout: page
title: Cut Line Threshold
description: >
  This tool removes or keeps entire lines based on a threshold input.
---

## Table of Contents
{:.no_toc}
0. this unordered seed list will be replaced by toc as unordered list
{:toc}


<html>
<body>

<iframe width="720" height="545" src="https://www.youtube.com/embed/3aVNAIIJ8sg">
</iframe>

</body>
</html>



## Prerequisites
None



## Manual Installation 
The following file(s) is the script placed in the somewhere in `$GALAXY_ROOT/tools/`.
* 'cut_line_threshold.py'
* 'cut_line_threshold.xml'
	
Then edit the '$GALAXY_ROOT/config/tool_conf.xml.main' and specify the path the '*.xml' was placed.

~~~
<toolbox>
.
.
.
    <section id="mat_tools" name="materials tools">
      <tool file="cut_line_threshold.xml" />
    </section>
~~~

* The file tag can also be in a subdirectory

## Running the Tests
Each 'Repository' has a subdirectory labelled 'test-data'. These are the files that are used as inputs to verify the functionality of the particular tool. This can be done manually by reading the README instructions for each repo or done automatically through the Toolshed installation process.


## Flags

~~~
usage: cut_line_threshold.py [-h] [-f TXT_FILE_PATH] [-t THRESHOLD_FLOAT]
                             [-c COLUMN_INT] [--comparator COMPARATOR_STR]
                             [--exclude] [--include]

optional arguments:
  -h, --help            show this help message and exit
  -f TXT_FILE_PATH, --file TXT_FILE_PATH
                        specify the data file location
  -t THRESHOLD_FLOAT, --threshold THRESHOLD_FLOAT
                        threshold value that a line is removed
  -c COLUMN_INT, --column COLUMN_INT
                        select column to denoise
  --comparator COMPARATOR_STR
                        set comparator type
  --exclude             remove lines inside the threshold
  --include             remove lines outside of the threshold
~~~

* '-f' specifies a tabular (csv) file input for processing.
* '-t' is the threshold value that the column values are compared against
* '-c' specifies on which column of data denoising executes
* '--comparator' this is comparator string that specifies what comparison is made:
	* <
	* ==
	* …  
* '--exclude' specifies that the satisfied condition is NOT returned
* '--include' specifies that the satisfied condition is returned


## Example

~~~
cut_line_threshold.py -f ./test-data/test.txt --comparator "<=" -c 6 -t "25.3" --exclude
~~~

## Acknowledgements 
* Original Galaxy Team
* To-do - Add Acknowledgements 