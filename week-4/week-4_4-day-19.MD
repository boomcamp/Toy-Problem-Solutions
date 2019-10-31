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
//DEFAULT
//Solution#1: Using isNaN, slice
function concat(str){
  var nums=[];
  var words=[];
  var end=0;
  
  for(var i=0;i<str.length;i++){
    if(isNaN(str[i])===true){
      words.push(str.slice(0,i+1));
      nums.push(0);
    }else if(isNaN(str[i])===false){
      nums.push(str[i]);
    }
  }
  //parseInt removes the preceding 0's. Try to find another method.
  end= parseInt(nums.join(''))+1
  return words[words.length-1] + end;
}

concat('Taco');
```
