`https://frontend.boom.camp/week-5/3-day-23/1-toy-problem`


```
//DEFAULT: DO NOT USE THIS

function validParens(string){
   var tokenizer = /[()]/g, // ignores characters in between; parentheses are
       count = 0,           // pretty useless if they're not grouping *something*
       token;
   while(token = tokenizer.exec(string), token !== null){
      if(token == "(") {
         count++;
      } else if(token == ")") {
         count--;
         if(count < 0) {
            return false;
         }
      }
   }
   return count == 0;
}

```

```
function validParens(string){
    let search = string.split('');
    let right = 0;
    let left  = 0;

    for(let i = 0; i < search.length; i++){
      if(search[i] == ")") right++;
      if(search[i] == "(") left++;
    }
    return(right === left);
}
```