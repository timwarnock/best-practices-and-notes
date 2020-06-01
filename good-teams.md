# Good Teams

What is a *Good* software engineering team? How would you measure that? 

*Notes from DevOps and Lean Software research.*

A good team will build quality products (services, platforms, etc) that solve real problems; and in order to be successful, a good team will require an inspiring vision, a Generative Culture, and the responsibility of fast / frequent deployments.

## The Vision

A successful organization must have an inspiring vision; and it must be shared so as to unite the different teams and technologies within the organization. Without an inspiring (and shared) vision, an organization will inevitably fall into a default Bureaucratic Culture (a rule-oriented culture). In that environment software developers will adopt what is known as a *mercenary mindset*. What's worse, due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law), these mercenary-minded developers will create technical output (products, services, platforms, etc) that reflect the bureaucratic communication channels between teams within the organization -- and they will NOT solve the problems of the users.

## The Measures

How would one measure a good team? Or more importantly, what can we easily measure that is a strong predictor for a high-performing software development team? 

It turns out, the following cluster of easy-to-measure metrics forms the best predictor of a high-performing team in a Generative Culture (a performance-oriented culture).

### Positive Measures

+ Deployment Frequency -- *how often do you deploy to production?*
+ Lead-Time -- *from code-commit to production*
+ Mean-Time-To-Repair (MTTR)
+ *Change Failure Rate*

More usefully, the first three (as a cluster) predict the *fourth measure*. In other words, the most stable systems (with the lowest failure rates) are the systems that have fast and frequent deployments in a fully-automated CI/CD pipeline. A fully automated CI/CD pipeline is an essential and necesary part of building quality software, but as we'll see, there's much more to consider.

### Negavitve Measures

In other words, what **NOT TO DO**? This may defy conventional wisdom, but the following are negative-predictors towards quality software. In other words, they are not only highly correlated with bad software, the mere existence of the following will predict a higher failure rate, as well as increased security risks.

+ Change Approval Board
+ Velocity -- *in the Agile/Scrum context*
+ Utilization -- *"as utilization approaches 100%, Lead-Time approaches infinity"*


### Meaningless Measures

Surprisingly, the following common measures provide no correlation whatsover between high-performing teams and low-performing teams. These are not negatively correlated (and thus may still be important factors within your organization); but they simply do not correlate to the overall quality and stability of your software, and should not be used as comparative measures.

+ Age of technology (mainframe vs distributed microservices)
+ Size of the organization
+ Whether Ops team or Dev team performs deployments
+ Unit-test coverage
+ Lines of code

This isn't to say that the above items are themselves meaningless, far from it, but it's important to understand that these measures will not predict the quality and stability of your software. For example, there are teams ingrating with ancient mainframes (and no unit-tests) that are outperforming teams with a microservice architecture and 100% unit-test coverage.

And while the size of an organization will not predict software quality, it is true that high-performing teams tend to scale much easier (scaling an organization requires a loosely coupled architecture more than anything else).


## The Culture

There are three categories of culture that one will find within software engineering organizations. Of these three, the Generative Culture (performance-oriented) is the one most likely produce quality software.

For more information see [Westrum Model of Organizational Culture](https://qualitysafety.bmj.com/content/13/suppl_2/ii22)


### Performance-oriented

Also known as *Generative Culture*, a Performance-oriented Culture values the mission of the organization over all else. It is in this environment where developers adopt a missionary mindset (rather than the more common mercenary mindset). Information flows easily, problems and failures are discussed openly (in fact, those discussions are encouraged).

Software created in a Performance-oriented Culture will tend to have a Loosely Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)), with deployments that are fast (minutes) and frequent (on-demand, several times per-day), taking full advantage of a fully automated CI/CD pipeline.


### Rule-oriented

Also known as *Bureaucratic Culture*, a Rule-oriented Culture values departmental goals over organizational goals. This is the most common culture in software engineering organizations, and it is the default culture for most large organizations. While often friendly, information flow is stymied by bureaucratic approvals, and problems are typically ignored. Often times the emphasis is on being nice and well-liked, rather than building quality software (and making users happy).

Software created in a Rule-oriented Culture will tend to have a Tightly Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)) and will reflect the particular bureaucratic communication channels between teams. There is likely a Change Approval Board, with deployments that are slower (measured in hours) and less-frequent (weekly or more) than what a fully automated CI/CD pipeline could otherwise provide.


### Power-oriented

Also known as *Pathological Culture*, a Power-oriented Culture values individual goals over organizational goals, where the loudest and most powerful voice in the room gets their way. Communication does not flow easily, and problems are typically suppressed.

Software created in a Power-oriented Culture will tend to have a Tightly Coupled architecture (due to [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)) and will reflect the particular whims of whoever has the most powerful voice (typically whoever is at the top of the hierarchy).


## Changing the Culture

The best way to change a culture is through an Inverse Conway Maneuver. Organize the teams and their communication channels to match the desired architecture. This will require cross-functional teams that adhere to Lean management, as well as a culture of Learning and Experimentation.

Conway's Law:

*"Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure."*

Inverse Conway Maneuver:

*"Make sure the organization is compatible with the product architecture."*


### Learning and Experimentation

Continuous learning

Team must be free to choose their tools, and change those tools as they the customer's problems are better understood.

Tool makers can not force the use of their tool!

Tools must make the developer's life easier. Just as a high-performing team focuses on solving the problems of their users, tool makers must treat other developers as their users and solve their problems (with attention to usability, accessibility, and customer satisfaction).

### Lean Management

*Adopt, Adapt, Adept*

+ Lightweight Change Management
+ Limited WIP
+ Visual Feedback (of production usage)

Compare this to a bureaucratic Change Approval Board, which in practice results in Risk Management Theater, or InfoSec Theater, rather than actual risk-managements and security.

The best visual feedback will tie small incremental changes to measures of customer satisfaction. For example, this could include user-engagement metrics, as well as feedback from advanced A/B testing (such as multi-armed-bandit algorithms).


## Refs

+ https://www.youtube.com/watch?v=RJz1GlClG1M
+ https://itrevolution.com/book/accelerate/
+ [Westrum Model](https://qualitysafety.bmj.com/content/13/suppl_2/ii22)

+ [Inverse Conway Maneuver](https://www.thoughtworks.com/radar/techniques/inverse-conway-maneuver)
