## Sam Valentine

I automate work that people are currently doing by hand.

My day job is accounts receivable leadership at a title insurance company, where I built the
automated deposit processing, weekly reporting, leadership dashboards, and failure alerting
behind a multimillion-dollar receivables operation spanning dozens of branch and agency
locations. I built all of it without
administrator access to the ERP, and that constraint shaped how I work: small pieces,
defensive defaults, and monitoring that stays quiet unless something genuinely needs a person.

The projects here are the other half. Each one is a domain I knew nothing about before
starting.

I use AI heavily and I am direct about that. I can specify, build, test, debug, and ship in
stacks I have not memorised, across mobile, backend, and desktop. The repositories below are
the evidence rather than the claim.

### Code

**[interval-sync](https://github.com/sam-valentine/interval-sync)**
Cloudflare Workers, D1, and KV. The sync backend behind Last Rep, and the shortest read of
anything here. Cross-device sync with no signup screen: the device generates its own id and
secret, the server stores only a SHA-256 hash of that secret, and bearer comparison is
constant-time. The README states the cost of that design out loud rather than hiding it, and
`schema.sql` explains why the workout blob stays in KV while only queryable data reaches D1.

**[last-call](https://github.com/sam-valentine/last-call)**
Android spam-call screener. Silences scam calls before the phone rings using on-device
heuristics plus a reputation list compiled from public FTC complaint data, served by a
Cloudflare Worker on a scheduled ingest. The screening engine is a pure function that checks
trust signals before suspicion signals, so a real contact can never be silenced by a heuristic.
It silences rather than rejects, because a hard reject tells an autodialer the line is live.

### Shipped

**Last Rep** ([try it](https://interval-timer-4bq.pages.dev))
Interval training and running app. One web codebase running as an installable PWA, shipping as
a native Android app, and shipping to iOS TestFlight without a Mac anywhere in the pipeline.
Source is closed while it is heading to the app stores. `interval-sync` above is its backend.

### Elsewhere

Clayton, NC. Reachable at sam.valentine@live.com
