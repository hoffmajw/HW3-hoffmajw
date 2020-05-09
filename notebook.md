**Design Issue: Balance Abstraction Using Factory Pattern**  
**Date: 5/6/2020**  
**Time Spent: 1 hr**  

**A. Factory Method**  
So we have products that must be made by a factory. These products all do the same thing, just in their own special way, and that is find the shortest path in the graph. I think if the story stopped here, we just had different algorithms or different representations of the graphs, then the Factory Method would be an appropriate solution to our problem. Our factory could simply create a breadth-first algorithm and not worry about the representation (only one), or maybe create your choice of representation but only use one algorithm. Because the client wants to be able to swap algorithms and representations, I think we should give them more control with the abstract factory. It would be easy to produce a 2D version and a list version of the graph, but once these graphs get traversed with multiple different algorithms, is breaks down.

**B. Abstract Factory**  
Like I stated before we could now allow clients to instantiate objects composed of different algorithms and different representations. The algorithms and representations behave independently and their concrete representations won't matter. I think the abstract factory pattern is utterly necessary to achive composition over inheritance in this situation of complex graph algorithms. The client could just be handed a graph of its own type that has an algorithm associated with it.

**Design Issue: Primary Functionality**  
**Date: 5/9/2020**
**Time Spent: **  

I think that the three use case scenarios are already decoupled from each other in a way. None of them really interact with each other. For instance, comparing representation implementation (US1) and comparing the actual algorithm implementation (US2) don't directly depend on each other. In US1's case, the algorithm serves just as a control, and the researcher can make sure they are testing the same algorithm to compare the representations. Likewise for US2, the representation is the control so algorithms can be compared. US3 is also highly decoupled, converting a graph to unweighted has nothing to do with its representation or algorithm. Because everything is so highly decoupled, I think we should take the singleton, transcript pattern approach over domain modeling. We don't really need to make any more abstractions to provide functionality. All the abstraction really lives in the data layer, creating the graphs of various representations and path implementations. The transcript pattern is strong suited to deal with simple logic and few transactions, and is an easy way to provide business logic for functionality that doesn't require many abstractions [1]. We are also told in the requirements document, that We don't need to worry about the presentation layer, as researchers will program to our API to visualize data. The transaction script will also seperate the UI from the operation for us [2].

**References**  
[1] https://dzone.com/articles/transaction-script-pattern  
[2] http://grahamberrisford.com/AM%202%20Methods%20support/06DesignPatternPairs/Domain%20Driven%20Design%20v.%20Transaction%20script.htm
