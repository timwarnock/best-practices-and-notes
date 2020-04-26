# Good Code?

+ https://www.youtube.com/watch?v=RJz1GlClG1M
+ https://itrevolution.com/book/accelerate/

What is (and what is not) good code? Specifically, what are the most meaningful measures of good code? How can one prove that code is good or bad?

Obviously, good code should be

  + high performing
  + secure
  + fault-tolerant

And while it's easy to list nice attributes of good code, from test coverage to a clean and readable style, good code always starts off as bad code. No one writes good code from scratch. We edit and massage bad code until it becomes better; we continuously test, and we demo our ***working*** software to our users, refining the code until it slowly approaches what might be considered good. 

But okay, is there any way to measure this objectively?


## high performance
An application should survive heavy load tests with reasonable performance characteristics. E.g., a well-designed HTTP "microservice" (yes, those are ironic quotes) should handle **at-least** 10,000 tps (transactions-per-second) on a single instance, and scale to 100,000 or even a million transactions-per-second without any significant degredation.

gatling.io

artillery.io


## secure
An application should be secure from obvious security exploits.

github.com/zaproxy/zaproxy

nmap

kali...


## fault tolerant
An application should provide a reasonable level of fault tolerance.

Unit+Integration Tests with an ***appropriate*** level of coverage, augmented by,

Mutation Testing: PIT, stryker, stryker4s

https://stryker-mutator.io/stryker4s/

