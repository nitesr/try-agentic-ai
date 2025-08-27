Langgraph vs Crew AI;
    Langgraph is more technical in its terminology - graph, node, edge, state, memory
        - each node can be treated as a agent
        - graph is a network of agents with flow logic on edges
        - state is a store for maintaining the state of current execution
        - memory is a store (db) for maintaing all the states of all executions

    Crew AI terminology uses agent domain language - role play, back story, focus, memory, tools, tasks, collaboratoin and gaurdrails.
        - Focus:
            - keep agent focussed and use multiple agents in case the focus is getting diluted
            - choose the tools for the agent, agents perform better when their are focussed (less) tools
        - Memory: remember and take new decisions based on the past. long-term, short-term and entity memory
            short-term: lives only during the crew execution (like state in langgraph)
            long-term: lives across executions and stored in db locally, learn from previous executions
            entity: short lived only during execution. stores what are the subjects - persons,organizations, locations, etc.
    
    


