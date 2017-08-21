Effective Eventual Consistency with Actor Models + Amazon Web Services


http://ndcsydney.com/talk/effective-eventual-consistency-with-actor-models-amazon-web-services/

Consistency /  Availability / Partition Tolerence

Reliability
Traceability
Speed
Accuracy


Actor model implementations
 - Akka.net, Orleans



 as you add scale out, the next issue was managing state

 Strong eventual consistency
 - as long as an algorithm can taken data in any order the outcomes will be in the same order

 (Weak) Eventual consistency - where order does matter to get the same order outcome

 CRDT https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type
Query (get the state)
Update (or add item)
Merge Operation - Commutative, Associative, Idempotent

