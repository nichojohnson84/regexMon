# RegexMon 
### (a helpful gist to start understanding "regular expressions" or "regex" for short)

The first time I looked at a regular expression I thought that it was anything but regular.  But as you learn about the meanings behind the symbols it starts to take shape.  I think of it in a similar way to a template that something needs to fit in.  Like on a form, if someone says "Enter email" you would know to enter an email. A person on the back end you would know that is where to look for the email.  But a computer needs a way to know if something matches the criteria of what you are supposed to have entered so it will use a regular expression to see if what was entered fits or matches. 

## Summary

Regular expressions are similar to narrowing a search for a missing person by describing characteristics.  If the person you are looking for is 4ft tall and 8 years old you can search much more easily especially if you are a computer that can take things very literaly. You can also let the expression know if something is mandatory or if it just is a possiblity.  You can make these as small or large as you want.  That can be to your advantage as well as disadvantage depending on how big the file you are searching is and how mny similar versions there are of what you are looking for.  But we will keep it simple.

Here is an example of a "regex" or "regular expression" that is often used.  This will look at a password to see if it contains letters and numbers and is at least 8 digits long.

/[A-Za-z0-9]{8,}/

Whatever we put inside the square brackets in this case is the characters we are looking for but be careful because if you add an exception it could mean you are looking for anything besides what is in the brackets.  

In our example, if you were to add a special character it would not match as it on contains Captial and lower case letters using "A-za-z" and any digits since we added "0-9".  

To test the length of the pasword and that it is at least 8 digits we use the curly brackets afterword starting with 8 but leaving the second number blank meaning for this password it can be as long as you want as long as there are no spaces or special charcters.  Only letters and numbers.  That is what is meant by {8,}.  This is a very simpified version.  For a sneak peek at how complex it could be in order to make the password secure but still be able to see what it contains would look more like this.

/(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[!?@#$%^&*()\-+\\\/.,:;"'{}\[\]<>~])[A-Za-z0-9!?@#$%^&*()\-+\\\/.,:;"'{}\[\]<>~]{8,}/

Below I will go over some of the symbols or special characters you see here to describe their purpose.  You can click the link to tak you to any of the components below to find what it looks like and its meaning.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

\G = The start of a match
^ = The beggining of a string.
$ = End of a sting
\A = The start of a string
\Z = End of a string
\z = Absolute end of a sting
\b = A word boundary
\B = Non-word Boundary
as you may already notice if somthing is capitalized it usually means the opposite of the lower case version.

### Quantifiers

These symbols will all come after a character or set.
* = Zero or more of something.  This is also known as greedy because it covers such a massive range
+ = One or more consecutive characters "aa"  "11"
{3 "or any other number"} = Exactly the number in the curly braces.
{3,} = as in our example above the first character means the lowest possible amount while nothing afterword means it can go as    high as possible
{3'6} = This has to be between 3 and 6 characters
*? This will match as few as possible.  This is also a lazy scenario
*+ =  This will match as many characters as possible.  This is also a gready scenario.

### OR Operator

This is simply putting a bar between two options "|" It means that either option on either side of the bar can be an option and it will still be a match.

### Character Classes

[] These square brackets let us know the options.  If you were to put them in the middle of a word it would mean that only one of those can be used.  A good example is the color grey or gray. You would indicate this by using "gr[ae]y" since there are no dashes or other charcters it has to be one of those two.

But in our example above if you remember it can indicate many options as in [a-z] meaning that any lowercase letter can be used in that spot.  You can also use a quantifier to eliminate a single or multiple options by putting a "^" sign in the brackets such as lo[^o]se meaning you are looking for lose and not loose.

### Flags

At the end of your search or regex you can put a flag so anything that comes after the final / is a flag to give you an extra direction.

/g = means Global
/m = means multiline
/i = Case insensitive
/x = Ignore Whitspace
/s = single line
/u = Unicode
/X = eXtra
/U = Ungreedy
/A = Anchor
/J = Duplicate the group

### Grouping and Capturing

() = This allows you to identify a group and add a quantifier to the entire group or to restrict alternation to the segment.

### Bracket Expressions

[] = we have somewhat covered these but its worth singling them out.  You can use it to make sure a certain character is in a certain spot like we did with gr[ae]y.  That example is known as a class. 

But if you put a hyphen inbetween the characters or "class" it becomes a set such as [A-Z] meaning anything in between those.

### Greedy and Lazy Match

Greedy = This means match longest possible string.

Lazy = This means match shortest possible string.

For example, the greedy h.+l matches 'hell' in 'hello' but the lazy h.+?l matches 'hel'

### Boundaries

If you see this, "\b", it is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

There are three different positions that qualify as word boundaries:

- Before the first character in the string, if the first character is a word character.
- After the last character in the string, if the last character is a word character.
- Between two characters in the string, where one is a word character and the other is not a word character.

### Back-references

\1 = you wnat to find a match but you can use \1x\1 to look for it more than once.

-Backreferences match the same text as previously matched by a capturing group.
-Most regex flavors support up to 99 capturing groups and double-digit backreferences. So \99 is a valid backreference if your regex has 99 capturing groups.

### Look-ahead and Look-behind

Lookahead and lookbehind, collectively called “lookaround” because they are at either the beginning or end of a sequence.

The difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match. That is why they are called “assertions”. They do not consume characters in the string, but only assert whether a match is possible or not. Lookaround allows you to create regular expressions that are impossible to create without them, or that would get very longwinded without them.

Either one can be postive or negative to help you narrow things further.

## Author

Nick Johnson https://github.com/nichojohnson84
