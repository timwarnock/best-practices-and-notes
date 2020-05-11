# Good Teams

What is a Good Software Engineering Team? How would you even measure that? 

*Notes from DevOps and Lean Software research.*

## The Goal

A successful organization must have an inspiring goal, a shared vision that unites different teams and technologies. Without an inspiring and shared goal, an organization will fall into a default Bureaucratic Culture (a rule-oriented culture). In that environment software developers will adopt what is known as a *mercenary mindset*. What's worse, due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law), these mercenary-minded developers will create products and services that reflect the bureaucratic communication channels between teams within the organization -- and will NOT meet the goals of the users.


## Measures

What to measure? Or more usefully, what can we easily measure that is a strong predictor for a high-performing software development team? It turns out, the following cluster of easy-to-measure metrics forms the best predictor of a high-performing team in a Generative Culture (a performance-oriented culture).

### Positive Measures

+ Deployment Frequency -- *how often do you deploy to production?*
+ Lead-Time -- *from code-commit to production*
+ Mean-Time-To-Repair (MTTR)
+ *Change Failure Rate*

More usefully, the first three (as a cluster) predict the *fourth measure*. In other words, the most stable systems (with the lowest failure rates) are the systems that have fast and most frequent deployments in a fully-automated CI/CD pipeline. A fully automated CI/CD pipeline is an essential and necesary piece of building quality software, but as we'll see, it's not so easy to do.

### Negavitve Measures

In other words, what **NOT TO DO**? This may defy conventional wisdom, but the following practices are negative-predictors towards quality software. In other words, they are not only highly correlated with bad software, the mere existence of the following will predict a higher failure rate, and increased security risks.

+ Change Approval Board
+ Velocity -- *in the Agile/Scrum context*
+ Utilization -- *"as utilization approaches 100%, Lead-Time approaches infinity"*


### Meaningless Measures

Surprisingly, the following common measures provide no strong correlation whatsover between high-performing teams and low-performing teams. These are not negatively correlated (and thus may still be important factors within your organization); but they simply do not correlate to the overall quality and stability of your software.

+ Age of technology (mainframe vs distributed microservices)
+ Size of the organization
+ Whether Ops team or Dev team performs deployments
+ Unit-test coverage
+ Lines of code

This isn't to say that any of the above is meaningless, far from it, but it's important to understand that these measures will not predict the quality and stability of your software. In other words, there are teams ingrating with an ancient mainframe (and no unit-tests) that are outperforming teams with a microservice architecture and 100% unit-test coverage.

And while size of an organization will not predict software quality, it is true that high-performing teams tend to scale much easier (although this is better predicted by loosely coupled architectures than anything else).


## Culture Matters

Westrum Model of Organiztaional Culture

### Power-oriented

Also known as *Pathological Culture*, a Power-oriented Culture values individual goals over organizational goals, where the loudest and most powerful voice in the room gets their way. Communication does not flow easily, and problems are typically suppressed.

Software created in a Power-oriented Culture will tend to be a Tightly Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)) that will reflect the particular whims of whoever has the most powerful voice (typically whoever is at the top of the hierarchy).


### Rule-oriented

Also known as *Bureaucratic Culture*, a Rule-oriented Culture values departmental goals over organizational goals, and is the default culture for most large organizations. While often friendly, information flow is stymied by bureaucratic approvals, and problems are typically ignored. Often times the emphasis is on being nice and well-liked, rather than building quality software (and making users happy).

Software created in a Rule-oriented Culture will tend to have a Tightly Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)) that will reflect the particular bureaucratic communication channels between teams. There is likely a Change Approval Board, with deployments that are slower (measured in hours) and less-frequent (weekly or more) than what a fully automated CI/CD pipeline could otherwise provide.


### Performance-oriented

Also known as *Generative Culture*, a Performance-oriented Culture values the mission of the organization over all else. It is in this environment where developers adopt a missionary mindset (rather than the more common mercenary mindset). Information flows easily, problems and failures are discussed openly (in fact, those discussions are encouraged).

Software created in a Performance-oriented Culture will tend to have a Loosely Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)), with deployments that are fast (minutes) and frequent (on-demand, several times per-day), taking full advantage of a fully automated CI/CD pipeline.


## Changing the Culture

See Conway's Law

*"Organisations often produce web sites with a content and structure which mirrors the internal concerns of the organisation rather than the needs of the users of the site."*

### Inverse Conway Maneuver

*"Make sure the organization is compatible with the product architecture."*



## Refs

+ https://www.youtube.com/watch?v=RJz1GlClG1M
+ https://itrevolution.com/book/accelerate/
+ [Westrum Model](https://qualitysafety.bmj.com/content/13/suppl_2/ii22)

+ [Inverse Conway Maneuver](https://www.thoughtworks.com/radar/techniques/inverse-conway-maneuver)
