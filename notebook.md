**Design Issue: Balance Abstraction Using Factory Pattern**  
**Date: 5/6/2020**  
**Time Spent: 1 hr**  

**A. Factory Method**  
So we have products that must be made by a factory. These products all do the same thing, just in their own special way, and that is find the shortest path in the graph. I think if the story stopped here, we just had different algorithms or different representations of the graphs, then the Factory Method would be an appropriate solution to our problem. Our factory could simply create a breadth-first algorithm and not worry about the representation (only one), or maybe create your choice of representation but only use one algorithm. Because the client wants to be able to swap algorithms and representations, I think we should give them more control with the abstract factory. It would be easy to produce a 2D version and a list version of the graph, but once these graphs get traversed with multiple different algorithms, is breaks down.

**B. Abstract Factory**  
Like I stated before we could now allow clients to instantiate objects composed of different algorithms and different representations. The algorithms and representations behave independently and their concrete representations won't matter. I think the abstract factory pattern is utterly necessary to achive composition over inheritance in this situation of complex graph algorithms. The client could just be handed a graph of its own type that has an algorithm associated with it.
