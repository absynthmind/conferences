# Key note

# What Makes a Great API?
- John Musser, API Science, Prog.Web
- API Science -> private beta (health and monitoring!)
- Benchmark: TTFHW!
-- Check Twillio API als voorbeeld
- Tools (voor adoption)
-- Check Twilio's debugger. APIGee API console (versus Groovy console!!!)
- Also: consistent resp. times

# API Security
- ING als IdP? Via OAuth? Is dat voldoende?
- Check OAuth Resource-Owner Password Creds voor OIA
- Check OpenID Connect
-- voor OIA
-- "federated handshake"
-- SAML Bearer Grant (of alt. JWT Bearer Grant)
-- Of [Insert Secret] Bearer Grant
-- Turns API provider into IdP
- Trend is towards bearer token iso. MAC
-- Bearer tokens need to be used responsibility
-- Exchanged over user channel
-- Fits internal scenarios(?)
- MAC is better protected against MiM (but need to keep 2 secrets/client)
- Advise: decouple API security from actual APIs
-- Configure, not code
-- Check L7 proposition

# Evolution of Netflix API
- "Discovery" vs. "Streaming". Topic is former
- 2011: requests blocking on latency in serving
- Netflix are optimised for speed of iteration 
- Teams are allowed to make own tech choices
- Hystrix to wrap requests
-- check!!! (" circuit breaker")
- Zuul routing layer (with rule engine) 
-- check
-- allows for canary versus baseline
-- allows for "squeeze" testing (route incremental traffic to node)
-- allows "coal mine": heavily instrumented instance for in-depth details. Long-lived Canary, really.
- Scryer to predict what the load will be
-- Predictive + reactive auto-scaling
- Experience-based APIs!!!!
- RxJava
- Basically have a "back-end" API, on top of which "Rest APIs" are build on top
-- SDK for API Web Service Development!!!
- Phyton script to run a piece of code on any code
 
# Scaling Ops at Facebook
- Renamed from AppOps to "Production Engineering"
- Gatekeeper: separates deployment of code from its activation
- Fixing in production is a kludge: problem introduced by dev; so what's the incentive for fixing?
- Outgrow off-the-shelf!!!

# Paypal
- Bij HomeDepot: betalen met 06-num en PIN
- Ook hier: HATEOAS console
- Elements of success:
-- Standards (naming, etc)
--- Paypal REST Cookbook(s) - Check!!!
--- To show how generic stuff (OAuth) applies to your stuff
- Quotes Web Services Cookbook (Subbo)
- Design process
-- U/C Analysis, Capability Mapping, Resource Modeling, API Spec, Feedback
-- Really the way any UX process works!!!
-- Makes a point, that can't go too coarse grained (as opposed to Netflix) because their dev community is too diverse
- Check GenIO (op Github) voor documentatie
-- Check dev portal
- Tip: make API's feel like a product
- No diff (really) between internal and external APIs)
- Also communicate minor version no and release no through headers
