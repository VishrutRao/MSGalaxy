---
layout: page
title: Denoise
description: >
  This tool is a simple 1-D denoising toolbox with diffenent approaches for denoising data
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
	* csv
	* scipy
	* numpy
	* argparse
	* sys


## Manual Installation 
The following file(s) is the script placed in the somewhere in `$GALAXY_ROOT/tools/`.
* 'denoise.py'
* 'denoise.xml'
	
Then edit the '$GALAXY_ROOT/config/tool_conf.xml.main' and specify the path the '*.xml' was placed.

~~~
<toolbox>
.
.
.
    <section id="mat_tools" name="materials tools">
      <tool file="denoise.xml" />
    </section>
~~~

* The file tag can also be in a subdirectory

## Running the Tests
Each 'Repository' has a subdirectory labelled 'test-data'. These are the files that are used as inputs to verify the functionality of the particular tool. This can be done manually by reading the README instructions for each repo or done automatically through the Toolshed installation process.


## Flags

~~~
usage: denoise.py [-h] [-f TXT_FILE_PATH] [-algo ALGO] [-c COLUMN_INT]
                  [-w WINDOW_INT] [-e]

optional arguments:
  -h, --help            show this help message and exit
  -f TXT_FILE_PATH, --file TXT_FILE_PATH
                        specify the data file location
  -algo ALGO, --algorithim ALGO
                        algorithim for denoising data
  -c COLUMN_INT, --column COLUMN_INT
                        select column to denoise
  -w WINDOW_INT, --window WINDOW_INT
                        window size to denoise
  -e, --exclude         ignore other columns from output
~~~

* '-f' specifies a tabular (csv) file input for processing.
* '-algo' specifies the particular algorithim that is used for denoising the data.
	* Currently only ”moving average” is configured.
* '-w' is the window sizes that the algorithim uses for comparing neighboring data points when denoising.
* '-c' specifies on which column of data denoising executes.
* '-e' specifies whether the stdout is only the denoised column


## Example

~~~
denoise.py -f ./test-data/test.txt -algo "moving average" -w 18 -c 3
~~~

## Acknowledgements 
* Original Galaxy Team
* To-do - Add Acknowledgements 