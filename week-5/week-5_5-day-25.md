`https://frontend.boom.camp/week-5/5-day-25/1-toy-problem`

```
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


    decode(){
       //TODO
    }
}

const cipher = new CaesarCipher(5) 
cipher.encode('Codewars');
```