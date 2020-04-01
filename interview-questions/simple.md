## Warm up

Q: When working on a new project, identify what you need and the steps you typically take before writing code.

Q: When working with performance constraints, what steps do you take to write optimal code?

Q: How do you typically test your code, how much of a role does QA play?

Q: What is the output from executing the following:

```
for (i = 0; i < 10; ++i) if (i = 0) print("hello\n");
```


## CS

Q: What is 63 in binary? 
```
Hint: what about 31, 15, 7 ?
Bonus: base-64 ?
```

Q: How do you write a bitmask to test for bit number 2?

Q: What are some practical uses for bit shifting?

Q: What is endianness and where can it be a concern? Network order is typically which type?

Q: What is the difference between a breadth-first and depth-first search?

Q: Explain the difference between an acyclic graph and a nested set.  Write pseudocode to convert a digraph to a nested set.  Explain the benefits of the chosen algorithm.

Q: What is a closure? Provide an example of usage.

Q: What is the difference between a class and an object?

Q: Define encapsulation and polymorphism. Why are they overrated?

Q: What is an iterator and when/why would for(;;) loops be better?


# “Full Stack”

Q: What is a DOCTYPE? Why would you ever include one in your document?

Q: How does one define a DOM element that has two separate CSS classes?

Q: What do HTTP response codes 301 and 302 indicate?

Q: Will an HTTP POST follow redirects?

Q: How would you do an HTTP POST redirect?

Q: What, if any, is the upper limit for the size of a query string?

Q: In the last web UI project you worked on, what does it look like if the stylesheet is removed?

Q: What is AJAX (the methodology, not just the acronym)

Q: Does XMLHttpRequest follow HTTP 302 redirects?

Q: Write a search method for the built-in JavaScript array class

Q: Write a JavaScript class with private static functions


## Java8 / Scala / FP

Q: What is an Optional (Option) and when is it useful?

Q: What is the difference between map and flatMap?

Q: What is Reflection? When is it appropriate to use?


## Python

Q: What is a docstring?

Q: Explain the difference between files, modules, classes and packages

Q: How do tuples, lists, dictionaries and sets differ?

Q: If you have a list of keys and a list of values, create a dictionary

Q: What is duck typing?  How does it differ from type checking?  How is it done in Python?

Q: How does Python pass function parameters?  By value or reference?

Q: Explain dictionary comprehensions


## POSIX

Q: Explain fork(), and how it differs from exec().

Q: Describe daemonization

Q: What are the primary differences between threads and processes?

Q: What signal is typically sent, by convention, to reload configuration?  How do you send that signal on command line?

Q: If you have installed a new dynamic library into a non-standard location, what steps must be taken for the system to recognize the new lib?
(/etc/ld.so.conf ldconfig)


## Perl

Q: What does 'perl -w' do?

Q: What is strict mode? How do you enable it?

Q: How do blessed references differ from regular ones?

Q: How do you (?#comment) a regular expression?


## SQL

Q: Describe LEFT, RIGHT, INNER, OUTER, and NATURAL joins

Q: Given the following schema, find all "people" records with two or less "tags"

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

A: possibilities,
```
SELECT name FROM people LEFT JOIN tags ON people.people_id = tags.people_id GROUP BY people.people_id HAVING COUNT(*) <= 2;

SELECT name FROM people NATURAL LEFT JOIN tags GROUP BY people.people_id HAVING COUNT(*) <= 2;
```


