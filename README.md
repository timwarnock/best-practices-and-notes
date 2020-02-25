# Good Code

+ https://www.youtube.com/watch?v=RJz1GlClG1M

The goal of this project is to bring some objectivity into the question of what is (and what is not) good code. Specifically, what are the most meaningful measures of good code? How can one prove that code is good or bad?

Good Code should be,

high performance

secure

fault-tolerant


## high performance
An application should survive heavy load tests with reasonable performance characteristics (e.g., a well-designed http microservice should handle **at-least** 10,000 tps (transactions-per-second) on a single instance, and scale to 100,000 tps without significant degredation).

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

