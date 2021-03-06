# Self Challenge

## Instructions

1. In your starter project, open the files in the `challenge3` directory.
2. Complete this exercise **individually, not in pairs**.
3. **If you need help understanding the instructions, please ask for help! Your instructor is happy to help clarify the instructions.**
4. **Attempt to complete each exercise -- if you are working on an exercise for longer than ten minutes, move on to the next one.**
5. Afterwards, please **submit your answers** via Slack (we'll cover how to do this after the time is up)!

## Exercises

```js
function each(array, func) {
  for (var i = 0; i < array.length; i++) {
    func(array[i], i);
  }
}

function filter(array, predicate) {
  var acc = [];
  each(array, function(element, i) {
    if (predicate(element, i)) {
      acc.push(element);
    }
  });
  return acc;
}

function map(array, func) {
  var acc = [];
  each(array, function(element, i) {
    acc.push(func(element, i));
  });
  return acc;
}
```

1. The following function `wordLengths` accepts a string as a parameter and
   returns an array of the lengths of each word in the string. Rewrite
   `wordLengths` using `each` (written above for your convenience); that is,
   replace the `for` loop.

   ```js
   function wordLengths(string) {
     var acc = [];
     var words = string.split(" ");
     for (var i = 0; i < words.length; i++) {
       acc.push(words[i].length);
     }
     return acc;
   }
   wordLengths("The quick brown fox jumps over the lazy dog")
   // => [ 3, 5, 5, 3, 5, 4, 3, 4, 3 ]
   ```

2. `wordLengths` involves *transforming* every word into its length, which makes
   this function an ideal use-case of the `map` abstraction. Using `map` (also
   written above for convenience), rewrite `wordLengths` (but write a new
   function, *e.g.* `wordLengthsMap`) again -- but this time using `map`.

3. Write a function called `wordsLongerThanThree` using `filter` that, given a
   **string** as input, returns an **array** of the words in the original string
   that are longer than three (have `length` greater than three).

    ```js
    wordsLongerThanThree("The quick brown fox jumps over the lazy dog")
    // => [ "quick", "brown", "jumps", "over", "lazy" ]
    ```
