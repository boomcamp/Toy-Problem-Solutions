
`https://frontend.boom.camp/week-5/1-day-21/1-toy-problem`


**BASIC**:

```
//Constant string literals
const alpha = {
  A: '@', B: '8', C: '(', D: 'D', E: '3', F: 'F', G: '6', H: '#',
  I: '!', J: 'J', K: 'K', L: '1', M: 'M', N: 'N', O: '0', P: 'P',
  Q: 'Q', R: 'R', S: '$', T: '7', U: 'U', V: 'V', W: 'W', X: 'X',
  Y: 'Y', Z: '2'
}
```

```
//Solution#1: Using .map()

function toLeet(str) {
  return str.toUpperCase().split('').map(letter=> alpha[letter]).join('');
}

//Solution#2: Using for loop

function toLeet(str) {
  let keys = str.toUpperCase();
  let splitt = keys.split('');
  let store = new Array();

  for(let i = 0; i < splitt.length; i++){
    store.push(alpha[splitt[i]])
  }
  return store.join('')
}
```

```
toLeet('leet') //=> '1337'
```


**ADVANCE**:

```
//TODO: 
```