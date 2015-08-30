# Analysis social network

This code is used in the simulation of the paper entitled "Influential Sustainability on Social Networks", ICDM 2015

## Four algorithms for analysis network

Four C++ files for deciding the putting seeds and time.

* Greedy.cpp
* IS_Break.cpp
* IS_UpperBound.cpp
* IS_Last.cpp

## Execution:

### Greedy:

```
$: g++ -o greedy Greedy.cpp
$: ./greedy edge.txt
```

Output file: greedy_put.txt

### IS_Break:

```
$: g++ -o break IS_Break.cpp
$: ./break edge.txt
```

Output file: break_put.txt

### IS_UpperBound

```
$: g++ -o upperbound IS_UpperBound.cpp
$: ./upperbound edge.txt
```

Output file: upperbound_put.txt

### IS_Last

```
$: g++ -o last IS_Last.cpp
$: ./last edge.txt
```

Output file: last_put.txt

## Edge file format

|   | start node | end node edge | rate |
|---|:----------:|:-------------:|-----:|
|Type|Interger|Interger|Float|

such as:

0 1 0.1

0 2 0.01

1 0 0.01

...

## Other File

### confirm.cpp

When we run the four algorithms, we usually run 1000 times. Then we use confirm.cpp to run the answer by these methods by 10000 times.

```
$: g++ -o confirm confirm.cpp
$: ./confirm edge.txt
```

Output file: confirm_put.txt

### random_method.cpp

This is random putting algorithm. The order of seed are random.

```
$: g++ -o random random_method.cpp
$: ./random edge.txt
```

Output file: random_put.txt

### run_all.cpp

This is to run all node as a seed. To see which node has the best influence.

```
$: g++ -o run_all run_all.cpp
$: ./run_all edge.txt
```

Output file: run_all.txt

### user.cpp

This is to know the information of each node, such as friends

```
$: g++ -o user user.cpp
$: ./user edge.txt outputfile
```

Output file: outputfile

## Some variables in [algorithm].cpp mean:

maxx ->It is the size of struct array used to save our node.

runtimes -> We use it to simulate that the node influences in network.

initnum -> It mean the number of seeds.

random_choice_thres -> We use it as a standard to choice some seeds which have some power of influence by random choose.

round_max -> It is the size of the array used to record the number of influenced nodes for each round.

thres1 -> The thresholds used to check whether these seeds influence one time of these round with the power.

thres2 -> It is not used now.

err -> To make sure the influence ability with no lucky random.
