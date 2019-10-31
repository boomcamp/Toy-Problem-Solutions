`https://frontend.boom.camp/week-4/5-day-20/1-toy-problem`

### Basic:

Variables:

```
let distance = 384000000;
let thickness = 0.0001;
let fold = 0;
```


```
//Solution#1: Using while loop
function foldToMoon(){
  while(thickness < distance){
    thickness *= 2; //0.0002 , 0.0004, 0.0008..
    console.log("Fold: ", (fold + 1) , ", Distance: ",thickness)
    fold ++
  }
  return "Folded: "+fold+" times";
}

foldToMoon();

Fold:  1 , Distance:  0.0002
Fold:  2 , Distance:  0.0004
Fold:  3 , Distance:  0.0008
Fold:  4 , Distance:  0.0016
Fold:  5 , Distance:  0.0032
Fold:  6 , Distance:  0.0064
Fold:  7 , Distance:  0.0128
Fold:  8 , Distance:  0.0256
Fold:  9 , Distance:  0.0512
Fold:  10 , Distance:  0.1024
Fold:  11 , Distance:  0.2048
Fold:  12 , Distance:  0.4096
Fold:  13 , Distance:  0.8192
Fold:  14 , Distance:  1.6384
Fold:  15 , Distance:  3.2768
Fold:  16 , Distance:  6.5536
Fold:  17 , Distance:  13.1072
Fold:  18 , Distance:  26.2144
Fold:  19 , Distance:  52.4288
Fold:  20 , Distance:  104.8576
Fold:  21 , Distance:  209.7152
Fold:  22 , Distance:  419.4304
Fold:  23 , Distance:  838.8608
Fold:  24 , Distance:  1677.7216
Fold:  25 , Distance:  3355.4432
Fold:  26 , Distance:  6710.8864
Fold:  27 , Distance:  13421.7728
Fold:  28 , Distance:  26843.5456
Fold:  29 , Distance:  53687.0912
Fold:  30 , Distance:  107374.1824
Fold:  31 , Distance:  214748.3648
Fold:  32 , Distance:  429496.7296
Fold:  33 , Distance:  858993.4592
Fold:  34 , Distance:  1717986.9184
Fold:  35 , Distance:  3435973.8368
Fold:  36 , Distance:  6871947.6736
Fold:  37 , Distance:  13743895.3472
Fold:  38 , Distance:  27487790.6944
Fold:  39 , Distance:  54975581.3888
Fold:  40 , Distance:  109951162.7776
Fold:  41 , Distance:  219902325.5552
Fold:  42 , Distance:  439804651.1104
=> 'Folded: 42 times'

```

