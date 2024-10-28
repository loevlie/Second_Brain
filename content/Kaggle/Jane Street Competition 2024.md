

## Helpful Resources

- Probabilistic transformer-based forecasting - https://huggingface.co/blog/time-series-transformers


# First Steps (Make a Repository)

1. We need an inference notebook that we can load models into and submit results
	1. Probably using the `polars` library
	2. Should try and modularize any sections that might change. 
		1. e.g. feature engineering, model evaluation (f(x) --> y)
2. New folder for each "experiment"
	1. Towards the end of the competition we should be able to benefit from a "ensemble of solutions" - https://www.kaggle.com/code/vyacheslavbolotin/jane-street-ensemble-of-solutions