# google_benchmark_plot

A python script to visualize the output from [google-benchmark][1]

Here is a 2 minute demo:

![2 minute demo](https://i.imgur.com/rEYqrWp.gif)

## Using the script

**If you are feeling lucky, try**
```
./your_benchmark_exe --benchmark_format=csv | python plot.py
```

### Detailed instructions

* Clone the repository
* Run `pip install -r requirements.txt` (works with both python 2 and 3)
* Obtain the benchmark results as a csv, this is done by running your benchmark as

```
./your_benchmark_exe --benchmark_format=csv > benchmark.csv
```

* Pass the csv file to this script

```
python plot.py -f benchmark.csv
```

### What else does it do

The script allows you to customize the plot using command line flags. The
complete help text can be seen by calling

```
$ python plot.py -h

usage: plot.py [-h] [-f FILE] [-m METRIC] [-t TRANSFORM] [-r RELATIVE_TO]
               [--xlabel XLABEL] [--ylabel YLABEL] [--title TITLE] [--logx]
               [--logy]

Visualize google-benchmark output

optional arguments:
  -h, --help       show this help message and exit
  -f FILE          path to file containing the csv benchmark data
  -m METRIC        metric to plot on the y-axis, valid choices are: real_time,
                   cpu_time, bytes_per_second, items_per_second
  -t TRANSFORM     transform to apply to the chosen metric, valid choices are:
                   inverse
  -r RELATIVE_TO   plot metrics relative to this label
  --xlabel XLABEL  label of the x-axis
  --ylabel YLABEL  label of the y-axis
  --title TITLE    title of the plot
  --logx           plot x-axis on a logarithmic scale
  --logy           plot y-axis on a logarithmic scale
```

[1]: https://github.com/google/benchmark
