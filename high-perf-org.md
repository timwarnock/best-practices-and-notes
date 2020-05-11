# High Performing Technology Organizations

Notes from DevOps and Lean Software research.

## The Goal

A successful organization must have an inspiring goal, a shared vision that unites different teams and technologies. Without an inspiring and shared goal, the organization will fall into a default Bureaucratic Culture (a rule-oriented culture). In that environment software developers will adopt what is known as a mercenary mindset. What's worse, due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law), these mercenary-minded developers will create products that reflect the departmental groupings of their bureaucracy -- and NOT meet the goals of the users.


## Measures

What to measure? Or more usefully, what can we easily measure that is a strong predictor for a high-performing software development team? It turns out, the following cluster of easy-to-measure metrics forms the best predictor of a high-performing team in a Generative Culture (a performance-oriented culture).

### Positive Measures

+ Lead-Time -- *from code commit to production*
+ Deployment Frequency -- *how often do you deploy to production?*
+ Mean-Time-To-Repair (MTTR)
+ Change Failure Rate

More usefully, the first three (as a cluster) predict the fourth measure. In other words, the most stable systems (with the lowest failure rates) are the systems that have fast and frequent deployments in a fully-automated CI/CD pipeline. This is an essential and necesary piece of building quality software, but as we'll see, a lot more is needed!

### Negavitve Measures

In other words, what should you **NOT DO**? These may defy conventional wisdom, but the following practices are negative-predictors towards quality software. In other words, they are not only highly correlated with bad software, the mere existence of the following will predict a lower quality of software, increased failure rate, and increased security risks.

+ Change Approval Board
+ Velocity -- *in the Scrum context*
+ Utilization -- *"as utilization approaches 100%, Lead-Time approaches infinity"*


### Meaningless Measures

+ Age of technology (mainframe vs distributed microservices)
+ Whether Ops team or Dev team performs deployments
+ Lines of Code



## Culture Matters




## Refs

+ https://www.youtube.com/watch?v=RJz1GlClG1M
+ https://itrevolution.com/book/accelerate/
+ [Westrum Model](https://qualitysafety.bmj.com/content/13/suppl_2/ii22)

