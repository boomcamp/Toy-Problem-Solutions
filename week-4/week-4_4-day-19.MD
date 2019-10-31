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
//Solution#1: Using switch case, typeof, isNaN

//Declare variables
let numbers=[];
let wordsOutput = [];
let zeros, computed, Zero;
let characters;
let nonZero = [];

//Holds actual result
let myReturn = [];

function WordCharacter(word = 'Tacos'){ //Set default string = Tacos

  for(var i=0;i<word.length;i++){
    
    //Cast into integer and assign all characters 
    characters = parseInt(word[i]);

     //Get only type numbers and NOT is not a number!
     if(typeof characters == 'number' && !isNaN(characters)){

       //Get thos numbers including zeros
       numbers[i] = characters;

       //Store those non Zero numbers
       if(characters !== 0) nonZero[i] = characters;

     }else{

       //Else, Store words and exclude 0 in array
       if(parseInt(word[i]) !== 0) wordsOutput.push(word[i])
     }
  }
 

 //Assign variables lengths for non zero and zeros
 let nonZerosLength = parseInt(nonZero.join('').length)
 let zerosAndNonZerosLength = numbers.join('').length;
  
  //Switch zeros and non zeros length to compare
  switch(zerosAndNonZerosLength){

    //Parameter found no zero then add 1
    case 0: 
     myReturn.push(wordsOutput.join('') , 1)
    break;
    
    //Numbers length found less than 3
    case 3:

    //Compute non zero 
     computed = parseInt(nonZero.join(''))+1;

     //Check non zeros length
     switch(nonZerosLength){
       case 1: Zero = "00" 
       break;

       default: Zero = ""  
       break;
     }
     myReturn.push(wordsOutput.join(''), Zero ,computed)
    break;
    
    //Numbers length found greater than 3
    case 4:
     computed = parseInt(nonZero.join(''))+1;
     myReturn.push(wordsOutput.join(''), (computed < 100 ? "00" : "0" ),computed)
    break;

  }
  
  return myReturn.join('');
}

//WordCharacter('Tacos'); //Tacos1
//WordCharacter('Word001'); //Word002
//WordCharacter('Word099') //Word100
//WordCharacter('Word0099') //Word0100
//WordCharacter('Word999') //Word1000

```
