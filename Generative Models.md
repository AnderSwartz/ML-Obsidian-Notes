Can take an example x and say "is this in the distribution?" p(x)

Why is this useful?
- Imagine a nuclear plant has a bunch of sensor readings. but there are many good sensor readings and few bad ones. So you can't build a typical classifier. But you can make a generative model of the distribution of good readings and then for a new reading, ask "is this in the distribution". -- Anomaly detection.
	- Often the space of positive examples is relatively small, while the space of neg samples is large (its like "everything else"). This makes it hard to model the negative space