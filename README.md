# Best Practices

+ https://www.youtube.com/watch?v=RJz1GlClG1M
+ https://itrevolution.com/book/accelerate/

The goal of this project is to bring some objectivity into the question of Software Engineering best practices, for example, what is (and what is not) good code. Specifically, what are the most meaningful measures of good code? How can one prove that code is good or bad?

Obviously, good code should be

high performaning

secure

fault-tolerant

And while it's easy to list nice attribuets of good code, from test coverage to clean and readable style, good code always starts off as bad code. No one starts writing good code, we edit and massage bad code until it becomes better; we continuously test, and we demo our ***working*** software to users and product managers, refining the code behind the scenes until it slowly approaches what might be considered good. But okay, what does that really mean?


## high performance
An application should survive heavy load tests with reasonable performance characteristics (e.g., a well-designed http microservice should handle **at-least** 10,000 tps (transactions-per-second) on a single instance, and scale to 100,000 or even a million transactions-per-second without any significant degredation).

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

