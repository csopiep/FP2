### JSON : Parsing and Writing

For the second exploration, I decided to take a look at the JSON library. Mainly because I'm familiar with it and I wanted to see how the library parses through a JSON file. It would be helpful knowing how to deal with multiple formats such as JSON, XML and HTML. Especially if I plan on making XML to JSON converter or vice versa. 

For starters I took my XML from FP1 and turned it into a JSON file with some slight modifications.
```JSON
{
  "Camelot": {
    "person": [
      { "name": "King Arthur" },
      { "gender": "Male" }
    ],
    "duty": { "Occupation": "King Of Camelot" }
  }
}
```
Then I wrote some code to start it off in order to see what the output was like.
```scheme
(define queen (open-input-file "Test.json"))
(define king (read-json queen))
```
To my suprise it didn't return a list but instead a hash table.
```
> king
'#hasheq((Camelot
          .
          #hasheq((person
                   .
                   (#hasheq((name . "King Arthur"))
                    #hasheq((gender . "Male"))))
                  (duty . #hasheq((Occupation . "King Of Camelot"))))))
```
I could change the hash table into a list but it leaves me with too many problems to deal with.
```
'((Camelot
   .
   #hasheq((person. (#hasheq((name . "King Arthur")) #hasheq((gender . "Male"))))
           (duty . #hasheq((Occupation . "King Of Camelot"))))))
```

Unforunately I wasn't able to learn how to manipulate hash tables in scheme yet due to time constraints.
