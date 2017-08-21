How one team built their first microservice

Valuestream maps
- time to build something across the JIRA boards (measured by the tool)
- 

- shows a large test time - time to stand up a build and test
    - chose microservices as a means of providing a way to CD
    - mountain climbing analogy of people tied together going up as fast as the slowest 
- What does a service look like
    - decoupled or more particularly autonomous 
- Choice of synchronous coupling is bad as the new system is coupled to the state of existing monolith
    - can compound as the number of services grew
- wanted to use a message bus, but that could be a while to get going
- just used a queue (named pipe) instead to solve 
- wanted to chose docker, .net core, AWS elastic services
- some new tech in backend, but no new tech everywhere
- Mediator library for command handler
- 

not transactionally processing
not event sourcing


consider likelihood, impact of assumptions

Anti corruption layer
- is the first thing that reads off the queueue
- a mapping of things from old db to new db, where a intermediate key was missing..
- 