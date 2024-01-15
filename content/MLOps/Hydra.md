
# High Level

## What is Hydra?

> Hydra is an open-source Python framework developed at Facebook AI Research that solves the problems outlined in Part 1 (and a few others), by allowing you to compose the configuration passed to your application. The composition can happen via your config file or the command-line, and everything in the composed config can also be overridden through the command-line.


## Problems with ML pipelines

- Config files tend to be monolithic 
- Changing config files is hard
	- It's difficult to keep track of the changes you make 
	- If you make new files each time this becomes tedious
- What about one big config file (what LoFTR does?)
	- [Medium Article](https://medium.com/pytorch/hydra-a-fresh-look-at-configuration-for-machine-learning-projects-50583186b710)
	
> You just end up with a big configuration file that knows about chosen two datasets, three architectures, and two loss functions. But wait, it turns out that your learning rate needs to be different when training on AlexNet versus ResNet50, and you somehow need to express this in the monolithic config file.

- Most of the time 90% of the config file is unused leading to it being difficult to determine the 10% that is important during runtime
- Building or overriding the config file at runtime from the command-line gives a powerful solution to both of these models.
	- This is part of what ==Hydra== helps with

- [f] Definitely worth a try!

