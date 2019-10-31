https://frontend.boom.camp/week-4/4-day-19/1-toy-problem

**Basic** :

```
//DEFAULT
//Solution#1: Using math operations Math.floor()

let arr = [];
let hours, minutes;

function validLength(actual, length = 1){
  return length.toString() === length
}

function humanReadable(seconds) {
  if (seconds < 360000) {	

    hours = Math.floor(seconds / 3600);
    minutes = Math.floor((seconds % 3600) / 60);
    seconds = Math.floor((seconds % 3600) % 60); 

    if (validLength(seconds,1)) 
      seconds = "0" + seconds;
    if (validLength(minutes,1)) 
      minutes = "0" + minutes;
    if (validLength(hours,1)) 
      hours = "0" + hours;
    
    return hours + ":" + minutes + ":" + seconds;
    
  } 
}

humanReadable(359999);
```

**Advance** :

```

```
