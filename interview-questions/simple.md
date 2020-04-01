# Questions for "Full Stack"

- Do you consider yourself front-end or back-end developer?
```
Full-stack? Guess again!
```
- Where in the stack are you strongest?


## Warm up

- When working on a new project, identify what you need and the steps you typically take before writing code.

- When working with performance constraints, what steps do you take to write optimal code?

- How do you typically test your code, how much of a role does QA play?

- What is the output from executing the following:
```
for (i = 0; i < 10; ++i) if (i = 0) print("hello\n");
```


## CS

- What is 63 in binary? 
```
Hint: what about 31, 15, 7 ?
Bonus: base-64 ? A-Za-z0-0+/
```

- How do you write a bitmask to test for bit number 2?

- What are some practical uses for bit shifting?

- What is endianness and where can it be a concern? Network order is typically which type?

- What is the difference between a breadth-first and depth-first search?

- Explain the difference between an acyclic graph and a nested set.  Write pseudocode to convert a digraph to a nested set.  Explain the benefits of the chosen algorithm.

- What is a closure? Provide an example of usage.

- What is the difference between a class and an object?

- Define encapsulation and polymorphism. Why are they overrated?

- What is an iterator and when/why would three-statement-for loops be better?


## Web

- What is a DOCTYPE? Why would you ever include one in your document?

- How does one define a DOM element that has two separate CSS classes?

- What do HTTP response codes 301 and 302 indicate?

- Will an HTTP POST follow redirects?

- How would you do an HTTP POST redirect?

- What, if any, is the upper limit for the size of a query string?

- In the last web UI project you worked on, what does it look like if the stylesheet is removed?

- What is AJAX (the methodology, not just the acronym)

- Does XMLHttpRequest follow HTTP 302 redirects?

- Write a search method for the built-in JavaScript array class

- Write a JavaScript class with private static functions


## Java8 / Scala / FP

- What is an Optional (Option) and when is it useful?

- What is the difference between `map` and `flatMap`?

- What is Reflection? When is it appropriate to use?


## Python

- What is a docstring?

- Explain the difference between files, modules, classes and packages

- How do tuples, lists, dictionaries and sets differ?

- If you have a list of keys and a list of values, create a dictionary

- What is duck typing?  How does it differ from type checking?  How is it done in Python?

- How does Python pass function parameters? By value? By reference?

- Explain dictionary comprehensions


## POSIX

- Explain fork(), and how it differs from exec().

- Describe daemonization

- What are the primary differences between threads and processes?

- What signal is typically sent, by convention, to reload configuration?  How do you send that signal on command line?

- If you have installed a new dynamic library into a non-standard location, what steps must be taken for the system to recognize the new lib?
```
e.g., 
LD_LIBARY_PATH or DYLD_LIBRARY_PATH
/etc/ld.so.conf
ldconfig
```


## Perl

- What does `perl -w` do?

- What is strict mode? How do you enable it?

- How do blessed references differ from regular ones?

- How do you `(?#comment)` a regular expression?


## SQL

- Describe `LEFT` and `RIGHT` joins? And `INNER` and `OUTER` joins? And `NATURAL` join?

- Given the following schema, find all `people` records with two or less `tags`

```
CREATE TABLE people (
  people_id INTEGER UNSIGNED NOT NULL PRIMARY KEY,
  name VARCHAR(255)
);

CREATE TABLE tags (
  people_id INTEGER UNSIGNED NOT NULL,
  tag VARCHAR(40),
  PRIMARY KEY(people_id, tag)
);
```

possibilities,
```
SELECT name 
FROM people 
LEFT JOIN tags ON people.people_id = tags.people_id 
GROUP BY people.people_id 
HAVING COUNT(*) <= 2;

SELECT name 
FROM people 
NATURAL LEFT JOIN tags 
GROUP BY people.people_id 
HAVING COUNT(*) <= 2;
```


## NoSQL

- What are the main advantages and disadvantages of NoSQL over SQL?

- How do you approach NoSQL data modelling?

- Is it possible and advisable to normalize a NoSQL data model?
