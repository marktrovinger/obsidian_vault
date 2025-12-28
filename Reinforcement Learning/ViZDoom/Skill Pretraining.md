**

- Creating a new map using an automated tool like Oblige is doable, but results in a map that is sub-optimal; they require a fair amount of tweaking to make usable for our purposes (enough that just creating the map might be roughly the same effort)
    
- Main skills in Doom:
    

- Navigation: My Way Home is the main environment that teaches an agent how to navigate from the starting location (which is randomized, I assume to prevent memorization) to a goal within 2100 timesteps
    
- Combat: DC, and the defend twins both teach the skill that enemies shoot at you and you need to shoot back
    
- Item collection: The health gathering twins do this fairly effectively, but there are some notable items that are not present for collection in the basic envs:
    

- Ammo: (I think, the combat envs start with a certain amount and there are no ways to acquire more)
    
- Keys: DT was tested on a key to door env, but a similar env doesn’t exist with the context of the basic Doom envs
    

- Level Interaction: There do not currently exist any basic envs that make use of either doors or switches within the game. This makes sense in the context of switches; they are used primarily to alter level geometry within the game, and that isn’t a skill that most agents need (yet). Doors are another story; they can be used in multiple ways within the game, most notably a door with a gold pattern texture is used to signify the end of the level within the single-player game.
    

- Pretraining
    

- Currently, we don’t use the skills learned in one map as the basis for a model trained on another map.
    

- Can we (does the infra exist) for us to load a model trained on My Way Home for 10 epochs and continue training for another 10 epochs in HGS, learning how to collect items on top of the existing skill of navigating the map?
    

- DM <-> simpler envs
    

- As the most complex of the basic envs (and one that doesn’t require engineering effort to add to SF), would there be value in taking a DM trained model and using that as a base for the simpler envs? Or could we Voltron-style a passable DM model using the simpler envs as components?
    

- LaMO used a pretrained model (on text), do we know what would be involved in doing something similar (this is not a well-thought out idea yet)
    

- If we did skill combination, do we have a good theoretical model for explanation of that behavior? (trying to get out ahead of reviewers saying we don’t explain things well enough)
    

- Map Creation
    

- Map size: My Way Home is the largest map (aside from DM, I think) in the basic envs, and contains a randomized start, and teaches a skill that would be required for a more complex agent
    
- Proposal: create variations using My Way Home as a base that add elements necessary for the acquisition of other skills; create a version that requires item pickup (through the use of the green slime for example) or a version that requires combat (one hallway could have monsters) or both (both hallways have monsters and not picking up a health pack would mean death)
    



**