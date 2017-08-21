Talk: Embracing Docker simplicity - while harnessing platform power

Michele Bustamente
@dasblonde


docker development tour

Create a couple of docker containers, but they can't talk to each other until dns is setup

you will need a container registry - when in on premise.local, you may end up using kubernetes or DC OS

#rundeck
a tool that gives a holistic view of builds and deployments in docker management

container deployment from terraform or ARM

Swarm scheduling / Orchestration
scheduling and constraints 

- implicit - ports, hardware etc
explicit - cpu, mem, io

determines node distribution - master / worker container


Orchestration / native ui
- docker enterprise edition (ee)
- 

load balancing, discovery
- Mesosphere DC/OS  / in Azure Container Services
    - Mesos/ Marathon load balancer

Recovery, Self healing, auto scale
Amazon ECS
Kubernetes / google Container Engine


