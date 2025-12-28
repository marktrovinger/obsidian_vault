## Questions 
#### What issue or gap does the paper address?
Learns a world model solely from image inputs. The actions taken by the agent are learned from the latent space that is constructed by images from the environment, which is from the world model. 
#### How was the research conducted? What framework or design was used?
##### Network Arch
World model has an image encoder (CNN), Recurrent State-Space Model, predictors for the image, reward and discount factor. Two distributions are computed from the recurrent state $h_t$: $z_t$ is the posterior state, which incorporates info from the current image, the prior state $\hat{z}_t$ is designed to predict the posterior without information about the current image.

The loss function optimizes the components of the world model jointly; the $-ln$ of the image loss, reward loss, discount loss, and the KL loss.

Uses an actor-critic to learn the long-horizon behaviors, the critic loss function regresses the $\lambda$-return using squared loss, and stops the gradients around the target (sg in equation 5). Actor loss is much more complicated, not sure I understand what is happening. 

##### Environments
The Atari environment was used, more specifically the Atari benchmark, which consists of 55 environments. 

#### What are the main results or takeaways?
Able to achieve either human-level or greater results on the Atari benchmark.

#### Any strengths? What’s effective or well-done in this paper?
The authors do a good job of explaining how the various components of the approach work; I never felt like the details were buried or glossed over.

#### Any weaknesses, limitations, assumptions, or critiques?
##### Critiques
The results from the humanoid experiments are not mentioned in the main paper, but rather as an appendix. This seemed odd; as the abstract mentions these results near the end, I would have liked to see these results in the main results section, but this was likely due to space restrictions from the venue in which the paper was published.

#### How does this connect to your research interests or projects?
Possible to use this approach for a multi-agent setting, would be interested to see if any work has been done in this direction.


## Wrap Up

### Next Paper Ideas
Do we want to meet and discuss multiple papers, and then discuss in depth one paper the week after?
- SMAC v2