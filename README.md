# ABOUT

This code snippet can be used to rip out probe intensity data from Affymetrix CEL files.
Only CEL file version 4 is supported (the binary version).
Probe intensity data is written into numpy arrays, to enable easy analysis.
Each CEL file contains 3 data points for each probe:

`(average pixel intensity, standard deviation of pixel intensity, number of pixels)`

Therefore, data for the first 10 probes should look similar to this:

    (7326.0, 875.0999755859375,  9)
    (162.0,  34.099998474121094, 9)
    (6933.0, 1001.0,             9)
    (224.0,  36.400001525878906, 9)
    (54.0,   6.0,                9)
    (247.0,  23.5,               9)
    (210.0,  18.299999237060547, 9)
    (207.0,  28.200000762939453, 9)
    (1147.0, 188.1999969482422,  9)
    (221.0,  24.200000762939453, 9)

The first column is exposed as numpy array `intensites`
The second column is exposed as numpy array `deviations`
The third column is exposed as numpy array `pixels`

In order to make any useful interpretation of this data
you need to use a PGF file and an up-to-date annotation
file, suitable for your CEL file.

# USAGE

Pass the name of the CEL file as the first and only argument to the script.
Execute the script with python3, for example:

`python3 parseCELfile.py 329975487_M.CEL`
