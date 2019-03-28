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
  -f [FMT [FMT ...]], --fmt [FMT [FMT ...]]
                        plot format, same convention as pyplot.plot() fmt
                        argument. Can be list where each item is format for
                        different y column
```

### The simplest example

For example, for the one column data structure ([example/sin.txt](example/sin.txt)):

```
0.8414709848078965
0.9092974268256817
...
-0.9992068341863537
```

To plot a line graph:

```bash
cplot example/sin.txt
```

![sin(x)](doc/fig_sin.png)

### Multiple columns, seperators and formats

For example, for the data structure ([example/multicol.txt](example/multicol.txt)):

```
x;y1;y2
1;10;30
2;20;20
3;30;10
```

To plot `x` vs `y1`:

```bash
cplot example/multicol.txt -s ";" -he -x 0 -y 1
# OR
cplot example/multicol.txt -s ";" -he -x x -y y1
```

![x vs y1](doc/fig_y1.png)

To plot `x` vs `y1` and `y2`:

```bash
cplot example/multicol.txt -s ";" -he -x x -y y1 y2
# OR
cplot example/multicol.txt -s ";" -he -x 0 -y 1 2
```

![x vs y1](doc/fig_y1-y2.png)

Changing the plot formats:

```bash
cplot example/multicol.txt -s ";" -he -x x -y y1 y2 -f bo r-
```

![x vs y1 with different fmt](doc/fig_y1-y2_fmt.png)

## Installation

You need Python installed, as well as Pandas and Matplotlib. Then, simply copy the `cplot` script to somewhere on your `$PATH`.

