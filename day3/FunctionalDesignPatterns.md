Functional Design pattern
#http://ndcsydney.com/talk/functional-design-patterns/

core principles of fp
- functions, types, compositios

functions as parameters
    - functions as interfaces
    - partial appln & DI
    - Continuations, chaining and the pyramid of doom
Monads
    - Error handling, Async
Maps
    - Dealing with wrapped data
    - Functors



    Core principles
        - Functions ar things
        - Composition everywhere
        - Types are not classes

    
    Designing with Composition -> functions all the way down
    type is not a class ->  it is just a set of data, no behavior

    Types can be composed -> they have no behavior, they are just data
    Algebraic type system => 
        use "AND" - * (F# syntax)
            - fruit salad => one each of apple and banana and cherry
        use "OR" - | (F)
            - snack  => apple or banana or cherry


            type snack = 
                | Apple of AppleVariety
                | Banana of BananaVariety
                | cherry of cherryvariety


use static types for domain modelling and documentation
fsharpforfunandprofit.com/DDD

lots of collection functions like this: fold, map, reduce, etc..

everything is a single parameter function
 -> Partial applications
 |> pipe operator from F#


use partial application 


Continuations - 

Pattern chaining

chaining continuations

bind

railway oriented programming

/fppaterns
Domain modeling made functional - > the pragmatic


    