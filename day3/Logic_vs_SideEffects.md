 Logic vs. side effects: functional goodness you don't hear about

 http://ndcsydney.com/talk/logic-vs-side-effects-functional-goodness-you-dont-hear-about/

 book author: Functional Programming in C#

Software Crisis
- inability to deliver s/w as per customers requirements
- Can't work with interview

Developer Priorities
- tools (75%)
- ideas (20%)
- Processes (5%)


Functional Programming
- a style that emphasizes functions, avoid state with 
- Power (do more with less code)
- safety (avoid state mutation)
- Clarity (functions as contracts, inputs -> outputs, nothing else)

Side effects and Pure
- Side Effects
    - Mutation funciton arguments
    - Throw Exceptions
    - Read/Write mutable global state
- Pure functions
    - no side effects
    - output solely detrmined solely by inputs

    - hence pure functions are easy to test, understand, optimize, parallelize, 
    - but they don't have side effects


    the key is side effects are needed
    logic is pure functions
    side effects is the outcome 

    - Throw Exceptions
        - Make the possibility of failure as standard
        - Error data is returned as payload


    Mutate global state
        - 

        Separate Concerns
            1. Representing State (data objects)
                - Product
            2. representing state transitions (functions)
            3. Assicating a objects en


    isolating i/o
    - dependency injection
    - dependency rejection
        - Mark Seemann - 
         - isolate logic (in pure functions - testable) & io (in impure functions - not testable)
    - Free Mondads
        - use data objects (POCOs) to represent instructions
        - logic produces a "list" of instructions
        - an interpreter translates the instructions in to side effects

    
    functional programming in C#
    Enrico Buonanno
    Manning, 2017
    DOTD code: dotd081817au