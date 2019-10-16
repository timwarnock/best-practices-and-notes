# good-code
Notes and best practices for automated testing.

A robust well-architected system SHOULD be **provably**

high performance

secure

fault-tolerant


## high performance
An application should survive heavy load tests with reasonable performance characteristics (e.g., a well-designed http microservice should handle **at-least** 10,000 transactions-per-second on a single ec2 instance, and scale to 100,000tps without significant degredation)

gatling.io
artillery.io

## secure
An application should be secure from obvious security exploits.

github.com/zaproxy/zaproxy
nmap
kali...

## fault tolerant
An application should provide a reasonable level of fault tolerance.

Unit+Integration Tests (provide a high-level of code coverage)
Mutation Testing: PIT, stryker, stryker4s
https://stryker-mutator.io/stryker4s/

