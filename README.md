# CPlot

A very simple matplotlib wrapper to plot columns from a data file. *Work in progress.*

## Usage

```
Plot some columns.

positional arguments:
  file                  path to the data file

optional arguments:
  -h, --help            show this help message and exit
  -s SEP, --sep SEP     the separator between columns in the data
  -x X, --x X           column representing x, defaults to None
  -y [Y [Y ...]], --y [Y [Y ...]]
                        column(s) representing y
  -he, --header         is the first row a header?
```

For example, for the data structure ([test.txt](./test.txt)):

```
x;y1;y2
1;10;30
2;20;20
3;30;10
```

To plot `x` vs `y1`:

```bash
cplot test.txt -s ";" -he -x 0 -y 1
# OR
cplot test.txt -s ";" -he -x x -y y1
```

![x vs y1](doc/fig_y1.png)

To plot `x` vs `y1` and `y2`:

```bash
cplot test.txt -s ";" -he -x x -y y1 y2
# OR
cplot test.txt -s ";" -he -x 0 -y 1 2
```

![x vs y1](doc/fig_y1-y2.png)

## Installation

You need Python installed, as well as Pandas and Matplotlib. Then, simply copy the `cplot` script to somewhere on your `$PATH`.

