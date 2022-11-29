# Mini-AlphaStar
Created: 2022-11-28 13:42

# Inspiration
Given the size and complexity of the AlphaStar algorithm, it makes experimenting with it both extremely complex and costly. It cites that it required 128,000 CPU cores and 384 TPU cores for 44 days of training, which almost certainly cost upwards of several hundred thousand dollars, if not millions of dollars.

The paper makes the point that while AS is very cool, it's not a perfect way to solve the SC2 problem; namely that it uses a reduced feature space, known as the *raw-level* API, not the *human-level* API. The differences mentioned is that the *raw-level* is much smaller in comparison to human level, but doesn't state what information is hidden in the raw-level API. The third point made is that some of the settings are tweaked to make things easier for the agent, and more difficult for human players to play against it. They also bring up that since so much human play is used to train AS, that the agent is more likely to imitate a human player than explore novel solutions.

# Methods
The paper breaks down the approach taken by first the AS paper, and then in comparison the mAS algorithm. They also list the approaches taken by the steps in the pipeline, and how various values are computed.

# Conclusion
They don't say much in the conclusion, mainly that they are going to continue working on it.

# My Conclusion
At this point, I'm not sure that looking at either AS or mAS is a valuable use of time; as both require fairly complex and computationally expensive setups, and even the less expensive of the two doesn't seem to offer much in the way of benefit. I will continue to examine it, but my conclusion at this time is that greater efforts are likely not going to bear much fruit.



## References
1. 