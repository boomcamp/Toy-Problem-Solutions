`https://frontend.boom.camp/week-4/1-day-16/1-toy-problem`


```
//Solution#1: Using Regular expression
function toCamelCase(string){
  return(string.replace(/(^|-|_)./g, s => s.slice(-1).toUpperCase()));
}

toCamelCase('the-stealth-warrior'); // returns 'theStealthWarrior'
toCamelCase('The_Stealth_Warrior'); // returns 'TheStealthWarrior'




//solution#2 : Using while loop
let keySearch, i;
let storage = []

keySearch = ["t","h","e","-","s","t","e","a","l","t","h","_","w","a","r","r","i","o","r"];

i = keySearch.length; //length

function toCamelCase(i,storage){
  while (i--) {
      //search key
      let position = keySearch[i] == "-" || keySearch[i] == "_";

      if (keySearch[i].length < i && position) {
          storage[i] = keySearch.splice(i, 1);         //remove
          storage[i] = keySearch[i].toUpperCase();     //convert upperformat
          storage[i+1] = ""                            //remove duplicate 
      }else{
        storage[i] = keySearch[i];
      }
  }
  return storage.join("")//output
}

toCamelCase(i,storage)



//Solution#3 : Using for loop
let holder = [];

function toCamelCase(str){
    let strings = str.split("");
    for(var i = 0; i < strings.length; i++){
       let position = strings[i] === "-" || strings[i] === "_"
       if(position){
          holder[i] = strings.splice(i,1)
          holder[i] = strings[i].toUpperCase() 
       }else{
          holder[i] = strings[i]
       }
    }

    return(holder.join(""))
}

toCamelCase('the-stealth_warrior');
```