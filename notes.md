Langgraph vs Crew AI;
    Langgraph is more technical in its terminology - graph, node, edge, state, memory
        - each node can be treated as a agent
        - graph is a network of agents with flow logic on edges
        - state is a store for maintaining the state of current execution
        - memory is a store (db) for maintaing all the states of all executions

    Crew AI terminology uses agent domain language - role play, back story, focus, memory, tools, tasks, collaboratoin and gaurdrails. Uses langchain internally.
        - Focus:
            - keep agent focussed (specific goals and objectives; narrowly defined tasks) and use multiple agents in case the focus is getting diluted
            - choose the tools for the agent, agents perform better when there are focussed (limited set of) tools
        - Memory: remember and take new decisions based on the past. long-term, short-term and entity memory
            short-term: lives only during the crew execution (like state in langgraph)
            long-term: lives across executions and stored in db locally, learn from previous executions
            entity: short lived only during execution. stores what are the subjects - persons,organizations, locations, etc.
        - Tools can be assigned to Agent and Task level. Task level is more specific.
            - Qualities:
                - versatile: confront fuzzy input and convert to strongly typed output (for api calls)
                - fault-tolerant: fail gracefully (self heal) and work with agent to retry 
                - caching: cross-agent caching tool calls
            - Examples:
                - search internet, scrape a website, call api, connect to db, send notifications, 
    
    


Issues:
    "The number of tokens to keep from the initial prompt is greater than the context length."

    Why ?
        prompt_tokens: system + user + tools + any RAG chunks
        prompt_tokens + max_output_tokens ≤ context_window
    
    Resolution:
        - Increase the context length (did in LMStudio)
        - Set "rolling window" for the context overflow (did in LM Studio)