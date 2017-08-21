talk 1: Talk: Confusion In The Land Of The Serverless

http://ndcsydney.com/talk/confusion-in-the-land-of-the-serverless/


#gartner cycle

computing resources get used as services without having to manage around physical capacities
Serverless Architectures mike roberts https://martinfowler.com/articles/serverless.html
#Photo

FAAS - Frontend as a Service
BAAS - Backend as a service


IAAS - Infrastructure As a Service
CAAS - Container as a Service
PaaS - Platform as a Service - FAAS/BAAS


Resliency - 


when you have a grid compute happening. the nodes that don't participate will become overloaded
thus the i/o points in the system need throttling mechanism


so the need for hybrid apps - how can you manage when you are sprouting serverless systems
refer to - Bustle - NDC serverless talks 
- 

HA across the application stack?

circuit breaker pattern to avoid breaking downstream services that are not scaled
- problem is that needs session - need per client state
- need throttling & load shedding middleware
#photo 



Security - 


