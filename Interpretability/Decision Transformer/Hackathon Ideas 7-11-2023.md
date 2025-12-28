Bloom's post: https://www.lesswrong.com/posts/bBuBDJBYHt39Q5zZy/decision-transformer-interpretability

-   Research tasks. Think more about how to exactly construct/interpret circuit analysis in the context of decision transformers. Translate ideas from LLMs/algorithmic tasks.

## Research Task TODOs
- Using the above as a prompt, start thinking about what has been covered, what hasn't been, and what seems likely that it can be tackled in a weekend
- Also, think about what software/infra work needs to be done before we can start
	- Can I run all of Bloom's code without issue, see Perusha's docs
		- https://docs.google.com/document/d/1qMXNApWcIlI_5szdEfnvvIjsdE6svgdhw_gqDlIJK98/edit#heading=h.l7toy8fx7mfq
		- The only issue I had was getting the WandB part working for the DT itself, but using that doc, I should be able to make it work
		- The code works, but the model that was saved doesn't seem to have layers beyond the first


## Research Ideas
- Measure cosine similarity between input directions of MLP neurons and directions of the OV circuit to provide more detail here. I plan to do this soon.
	- Did he ever do this?
- Implement extra analyses such as activation patching or checking for composition directly between attention heads and MLPs. 

