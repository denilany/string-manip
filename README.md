## Text Completion, Editing, and Auto-Correction Tool

## Objectives
This project aims to modify (manipulate) a string that has been stored in the text file "sample.txt" (input) and stores the manipulated text in the file "result.txt" (output).

### Introduction
The project is written in Go and adheres to good coding practices. The tool receives two file names as arguments from the command line: one containing the text to modify (input) and the other to store the modified text (output). The tool performs the following modifications:

1. Convert hexadecimal numbers preceded by "(hex)" to their decimal equivalent, (Ex: "1E (hex) files were added" -> "30 files were added").

2. Convert binary numbers preceded by "(bin)" to their decimal equivalent, (Ex: "It has been 10 (bin) years" -> "It has been 2 years").

3. Convert words preceded by "(up)" to uppercase, (Ex: "Ready, set, go (up) !" -> "Ready, set, GO !").

4. Convert words preceded by "(low)" to lowercase, (Ex: "I should stop SHOUTING (low)" -> "I should stop shouting").

5. Convert words preceded by "(cap)" to capitalized, (Ex: "Welcome to the Brooklyn bridge (cap)" -> "Welcome to the Brooklyn Bridge").

6. Optionally, convert the specified number of preceding words to lowercase, uppercase, or capitalized, (Ex: "This is so exciting (up, 2)" -> "This is SO EXCITING").

7. Correct punctuation placement for ".", ",", "!", "?", ":", and ";". Every instance of the punctuations should be close to the previous word and with space apart from the next one, (Ex: "I was sitting over there ,and then BAMM !!" -> "I was sitting over there, and then BAMM!!").

8. Format groups of punctuation marks like "...", "!?", etc. (EX: "I was thinking ... You were right" -> "I was thinking... You were right".)

9. Place single quotation ' marks properly around words, they should be placed to the right and left of the word in the middle of them, without any spaces. (Ex: "I am exactly how they describe me: ' awesome '" -> "I am exactly how they describe me: 'awesome'")


10. Replace "a" with "an" if the next word begins with a vowel (a, e, i, o, u) or a h. (Ex: "There it was. A amazing rock!" -> "There it was. An amazing rock!").

### Allowed Packages
Only standard Go packages are allowed for this project.

### Usage

<pre>$ cat sample.txt
it (cap) was the best of times, it was the worst of times (up) , it was the age of wisdom, it was the age of foolishness (cap, 6) , it was the epoch of belief, it was the epoch of incredulity, it was the season of Light, it was the season of darkness, it was the spring of hope, IT WAS THE (low, 3) winter of despair.
$ go run . sample.txt result.txt
$ cat result.txt
It was the best of times, it was the worst of TIMES, it was the age of wisdom, It Was The Age Of Foolishness, it was the epoch of belief, it was the epoch of incredulity, it was the season of Light, it was the season of darkness, it was the spring of hope, it was the winter of despair.
$ cat sample.txt
Simply add 42 (hex) and 10 (bin) and you will see the result is 68.
$ go run . sample.txt result.txt
$ cat result.txt
Simply add 66 and 2 and you will see the result is 68.
$ cat sample.txt
There is no greater agony than bearing a untold story inside you.
$ go run . sample.txt result.txt
$ cat result.txt
There is no greater agony than bearing an untold story inside you.
$ cat sample.txt
Punctuation tests are ... kinda boring ,don't you think !?
$ go run . sample.txt result.txt
$ cat result.txt
Punctuation tests are... kinda boring, don't you think!?</pre>