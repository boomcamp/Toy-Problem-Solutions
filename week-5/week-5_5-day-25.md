`https://frontend.boom.camp/week-5/5-day-25/1-toy-problem`


```
//Solution#1: Using regex

function CaesarCipher(offset) {
  const a = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
  const regex = /[a-z]/gi
  
  this.encode = function(str) {
    return str.replace(regex, function(letter) {
      return a[(a.indexOf(letter.toUpperCase()) + offset) % 26]
    })
  }
  
  this.decode = function(str) {
    return str.replace(regex, function(letter) {
      return a[(a.indexOf(letter.toUpperCase()) + 26 - offset) % 26]
    })
  }
};
```

```
Solution#2 : Using index manipulation


//ES6 Class Style

class CaesarCipher {
    constructor(seed) {
        this.word = [];
        this.seed = seed;
        this.alphabet = 'abcdefghijklmnopqrstuvwxyz';
    }

    encode(str) {
      let char, newIndex;

      for (let i = 0; i < str.length; i++) {
        //We need to compare into lowercase format
        char = str[i].toLowerCase();

        //if inside the index
        if (this.alphabet.indexOf(char) > -1) {
            //move index from its original position
            newIndex = this.alphabet.indexOf(char) + this.seed; 

            //Check if index is less than the length of alphabet then pick letters from its new position
            if(newIndex < this.alphabet.length) {
              this.word.push(this.alphabet[newIndex])
            
            //Else shift alphabets length minus the new index position
            } else {
              var shiftedIndex = -(this.alphabet.length - newIndex);
              this.word.push(this.alphabet[shiftedIndex])
            }
        } 
    }
    //Convert to uppercase format
    return this.word.join('').toUpperCase();
    }


    decode(str){
        let char, newIndex;

      for (let i = 0; i < str.length; i++) {
        //We need to compare into lowercase format
        char = str[i].toLowerCase();

        //if inside the index
        if (this.alphabet.indexOf(char) > -1) {

            //Minus index from its original position then add 26 length
            newIndex = this.alphabet.indexOf(char) - this.seed + 26; 

            //Check if index is less than the length of alphabet then pick letters from its new position
            if(newIndex < this.alphabet.length) {
              this.word.push(this.alphabet[newIndex])
            
            //Else shift alphabets length minus the new index position modulo 26
            } else {
              var shiftedIndex = -(this.alphabet.length - newIndex) % 26;
              this.word.push(this.alphabet[shiftedIndex])
            }
        } 
      }
      //Convert to uppercase format
      return this.word.join('').toUpperCase();
    }
}

```

```
const c = new CaesarCipher(5);
//c.encode('Codewars'); // returns `HTIJBFWX`
//c.decode('BFKKQJX'); // returns `WAFFLES`
```