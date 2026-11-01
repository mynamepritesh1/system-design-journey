The core idea

System design questions have no single right answer. What gets evaluated is how you think: do you pin down the problem, reason with numbers, and explain trade-offs? Memorized architectures fail the moment the interviewer changes one requirement.

The biggest mistake is jumping straight to boxes (“add Kafka, add Redis”). The design should follow from the requirements, not the other way around.

A repeatable framework

For a ~45-minute design, use this order:

Step	Time	What you do
1. Clarify requirements	~5 min	Ask questions, fix scope, state what’s out of scope
2. Estimate scale	~5 min	Users, requests per second, storage (Day 2 covers the math)
3. API and data model	~5–10 min	Main endpoints, core entities
4. High-level design	~10–15 min	The main components and how data flows between them
5. Deep dive and bottlenecks	~10–15 min	Pick 1–2 hard parts, discuss trade-offs and failures
6. Wrap up	~2 min	Monitoring, future improvements, what you’d do next
Step 1 in detail: requirements

Functional requirements are what the system does. Example for a URL shortener: create a short link, redirect to the original, optionally let links expire.

Non-functional requirements are how well it does it. These drive most architecture decisions:

Scale: how many users and requests?
Latency: how fast must it respond?
Availability: what happens if it’s down for a minute?
Consistency: is stale data acceptable?
Durability: can we ever lose data?
Security: who can access what?

A good habit is to say “out of scope” explicitly, for example “I’ll skip analytics and user accounts unless you want them.” It shows you can control scope.

Worked example: “Design a URL shortener”

Good clarifying questions:

Is it read-heavy or write-heavy? (Redirects vastly outnumber creations.)
Roughly how many new URLs per day, and for how long do we keep them?
Do users pick custom aliases?
Is a redirect delay of a few hundred ms acceptable?
Is it okay if a link occasionally fails to resolve, or must it be highly available?

The answers decide a lot. “Reads are 100x writes, and redirects must be fast and almost always available” points straight at caching and replication. Without asking, you’d be guessing.

From your own experience

In ZenWorks, the requirement “each tenant’s data must be isolated” is what led to tenant-aware routing at the gateway and a data-isolation strategy. The requirement came first and the components followed. That is the same pattern you’ll use in every interview.

Common mistakes
Starting with technology instead of requirements.
Naming tools without saying why (“I’ll use Kafka” with no reason).
Skipping numbers, so you can’t tell whether you need one database or fifty.
Never stating trade-offs. Every choice costs something, and saying so is half the grade.
Going deep on a detail nobody asked about while ignoring the main flow.
Self-test (answer without looking)
Give two functional and two non-functional requirements for a chat app.
Why is “reads are 100x writes” useful information when designing?
Why should you state what is out of scope?
Today’s exercise

Take the prompt “Design a notification system” and write only the clarifying questions you’d ask, and the requirements you’d set (functional, non-functional, out of scope). Don’t design anything yet.
