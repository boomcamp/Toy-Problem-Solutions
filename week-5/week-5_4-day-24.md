`https://frontend.boom.camp/week-5/4-day-24/1-toy-problem`


```
//Solution: Using for loop

function accum(strings){
    let store = [];
    let letters = strings.split('');
    const accumulator = letters.length;
    
    for(let i = 0; i < accumulator; i++){
      const upperFormat = letters[i].toUpperCase();
      store.push(upperFormat) //Store uppercase format first ABCD

      //loop remaining lowercase letters, j = 1,2,3
      //letters[i] = b,cc,ddd
      for(j=1;j<=i;j++){
        store.push(letters[i])
      }

      //accumulator = 4, minus 1 = 3
      if(i<accumulator-1){
        store.push('-')
      }
    }
    return store.join('')
}

```

```
accum('abcd');
```