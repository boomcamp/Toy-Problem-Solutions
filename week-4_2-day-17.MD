`https://frontend.boom.camp/week-4/2-day-17/1-toy-problem`


### Basic:

```

//Solution#1: .map()

function squareEach(num){
  return parseInt((num.toString().split('').map(function(value){
    return value * value
  })).join(""))
}



//Solution#2: do,while 

let items ;
let i = 0; 
let holder = [];

squareEach = ListItems => {
	items = (ListItems).toString().split("")
	i = 0; 
  holder = [];

	do {
	  holder.push(items[i] * items[i]);
	  i++;
	}
	while (i < items.length);

  return parseInt(holder.join(""));
};



//Solution#3: for loop

function squareEach(items){
  let holder = [];
  let toSquares = items.toString().split("")

  for(var i = 0; i < toSquares.length; i++){
    holder[i] = toSquares[i] * toSquares[i] 
  }
  return parseInt(holder.join(""));
}



//Solution#4: forEach

function squareEach(items){
  let holder = [];
  items.toString().split("").forEach(function(value,index) {
     holder[index] = value * value 
  });
  return parseInt(holder.join(""));
}



squareEach(9119)
squareEach(4232)
```


### Advance:


```
//DEFAULT Solution#1: number + next count

function countdown(n){
//This is a 30 character solution
return((n+2) + "!" +(n+1) + "!" + (n))
}


countdown(3)
countdown(10)
countdown(100)


//Solution#2: Extracted example using class object
//Declare string literals 
let cDownEnums = {
  indexZero : 0,
  actualLength : 3,
  holder: [],
  result : [],
  parts :  "",
  concat : "",
};

//Object countdown
class countdown{
}

//Instantiate obj countdown
cDown = new countdown();

//Holds numeric numbers only
countdown.prototype.getStorage = function(n){ 

  while(true){
	  cDownEnums.holder.push(n)

    //if the increment (n) results to negative one it will break the loop!, then we need to n++ instead n--
    if(n == -1) n++; 

    //range is from 1 to N so we need to break tha loop for only 3 numbers
		if(cDownEnums.holder.length === cDownEnums.actualLength) break;
	}

  //returns list[n,n,n]
	return cDownEnums.holder;
}

//Add punctuation to numeric numbers
countdown.prototype.addPunctuation = function(n){ 
   
   //Get database
   cDownEnums.parts = cDown.getStorage(n);
    
    //Iterate loop
    cDownEnums.parts.forEach(function(items,index){
     
     //Declare lastposition element
     let lastPosition = (index < cDownEnums.parts.length - 1);

     //Do not add exclamation to last numbers1
     cDownEnums.concat = lastPosition  
     ?  cDownEnums.concat = "!" 
     :  cDownEnums.concat = "";
     
     //index is incremental, so reset index back to zero
     index = cDownEnums.indexZero; 
     
     //Declare result as string literal obj
     let literalResult = {
       result : (
         cDownEnums.parts[index]+2)+cDownEnums.concat
         +(cDownEnums.parts[index]+1)+cDownEnums.concat
         +(cDownEnums.parts[index]
       )

      
     };

     //the actual result
     cDownEnums.result.push(literalResult);

    })
   
    //Splice remaining first index from second position
    cDownEnums.result.splice(1,2)

   //Get the first index only!, it will iterate depends on the length
   return cDownEnums.result[cDownEnums.indexZero]
}


//Output
cDown.addPunctuation(100).result;
//cDown.addPunctuation(10).result;
//cDown.addPunctuation(100).result

```
