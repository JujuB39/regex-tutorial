# Matching an Email 
For this project I will be explaining how we use the regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` to match an email. I will go in depth of all the regex components this expressions utilizes, explaing what it means and how it is used. 

## Summary
A regular expression, also known as a regex is a sequence of characters that define a search pattern. It is mainly used to find patterns within a string. Regex are commonly used in a variety of coding languages such as PERL, Javascript, etc. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components
This regex includes a variety of components such as anchors, quantifiers, character classes, grouping and capturing, bracket expression, and greedy and lazy matches. While this expression uses several components this is not all the components a regex can utilize. Some of the other common components in a regex that are not utilized in this example of matching an email are: boundaries, flags, OR operators, back references, and look ahead and look behind. One of the most important parts however to start understanding how we can read this expression is to remember that a regex is considered a literal so the pattern must be wrapped in "/". 

### Anchors
Anchors do not match any character in the regex, instead they are used to declare
something about the string, specifically the position in the string. This regex uses two different types of anchors. The first anchor is the "^" which signifies the beginning of a string. The second anchor is a "$" which signifies the end of the string. 
   
### Quantifiers
Quatifiers specify how many times a specific character, group or character class must be present in order for a match to be found. It is important to note that quantifiers are also known as greedy, meaning that the regex will match as many occurences of a given patern. In this regex there are two quantifiers, "+" and "{}". The "+" symbol means that it will match the patern one or more times. In this instance there is a "+" in two places one after the first bracket expression and one after the second bracket expression. The second quantifier is the "{}". In this regex there is one set or "{}" that is written directly after the last bracket expression: `[a-z\.]{2,6}`. These curly brackets allows the user to set limits to a match. In this case this quantifier tells us that the final bracket expression of our regex is searching for any string that has a minimum of two characters and has a mazimum of six characters.

### Character Classes
A character class is anything that appears inside square brackets. One of the character classes we have inside our brackets is "/d" which will match any single number that is between 0-9. It is important to note that this will only match a single digit. Another character classs inside our brackets we see is a-z, which will match any letter between a-z. Remember that regex is case sensitive so this will be looking at only lowercase letters. Next we have 0-9 which will look for any digit from 0-9. We also have "\." (this is a character not a character class) which is looking for a ".". You may be wondering why it has a "\" before the period, the answer to that is simple, the "." in regex is a metacharacter which on it own will stand for any character. In this example we want "." to actually just look for the "." character so we have to use a character escape ("\"). Lastly the other things we are looking for inside the brackets are "_ and -" which are characters not character classes. 


### Grouping and Capturing
In this example our bracket expression are seperated into three groups and are divided by the "@" and "\." which will later group them toether. Remember as discussed in the previous section "\" is a character escape so "\." means there must be a "." before the beginning of the third group in order to actually define the third group. The "@" breaks up the first and second bracket expression: the first being the email username and the second being the email service. The "\." breaks up the second and the third capturing group: the third group being the domain neame. The first capturing group which matches the users email name is : `([a-z0-9_\.-]+)`. The second capturing group which matches email service is `([\da-z\.-]+)`. And the last capturing group which captures the domain name is `([a-z\.]{2,6})` 
 
### Bracket Expressions
In a bracket expression anything inside the square brackets represents a list of characters and/or character classs the user wants to match. In the example for email validations we have three bracker expressions which are : `[a-z0-9_\.-]`, `[\da-z\.-]`, and `[a-z\.]`. There are a couple of things we are looking to match here and they are: "a-z", "0-9", "_","-","\.", and "/d". The first one we will look at is "a-z", which will match any letter a-z (remember regex is case sensitive so it will only match lowercase letters). The next one is "0-9" which will match any number ranging from 0-9. The next two are just searching for those specific characters. The "\." is looking for a "." but it needs a character escape so that it isn't seen as a metacharacter instead. The last one, "/d" is looking for a single digit from 0-9. As mentioned before this will only match a single digit. Therefore it will match the number 3 but will not match the number 39 or 390.    


### Greedy and Lazy Match
As previously discussed in the quantifiers section, quantifiers are also considered greedy. So in this example we do have greedy matches. We have the "+" quantifier and the "{} quantifier. The "+" will match as many times as possible returning back as needed. This is used for the first and second capturing group. The {} quantifier will limit how many characters it wants to capture. In this example for our last capturing group we have {2,6} with two being the minimum amount and 6 being the maximum. This means in the last group it will be searching for a minimum of two characters and will not exceed six characters. 

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
