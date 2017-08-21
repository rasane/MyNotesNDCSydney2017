

monitoring application 
- monitoring specific for business needs
- diagnostics flow from ground up

plan
- use a hierarchical monitoring strategy
- lightweight for continuous and frequent monitoring  - cpu, mem, disk
- medium for less frequent events - rare exceptions, deadlocks
- Invasive for deep-dive and concrete diagnostics - memory leaks, bulk call-stack data (e.g cpu profiling)



Tools
- Performance counters
    - Provide numeric information
    - GetProcessTimes, GetProcessMemoryInfo
- ETW - halfway monitoring tools
    - evaluate logs
- ClrMD - programatic apis which only available through fully fledged debugger
    - https://github.com/Microsoft/clrmd
    - https://github.com/Microsoft/clrmd/blob/master/Documentation/GettingStarted.md
Invasive
    - Clr profiling
    - clr debugging


- 
    https://github.com/goldshtn/LiveStacks
- 


Monitoring for GC - memory 
- derive from eventStacksMonitor


Memory analysis:
LeakMonitor => implements a Monitor


Deadlock Detection
 - low cpu, requet timeouts, increased timeout
 attach clrMD to create wait chains and detect deadlocks
 Report the scenario - since there is not much that can 


 pros are obvious - greater visibility and hence ease scaling

 Cons
 - add complexity - reduce risk by using separate process - external process for management
    - containerized environment - separate container for host management - sys* monitoring container
- Adds overhead
- requires dev
