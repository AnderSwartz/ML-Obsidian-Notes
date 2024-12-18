Scaling is important because the features with the most variation might take over. 
For some models like linear regression, scaling is not supposed to help
Just like you can't take the test data into consideration when "fitting" the scaling, you cant do this with the validation data either
# Standard scalar
Results in the mean for all data points across all dims being 0
# Min max scalar
Maps min and max values to specific values. "Make my min 0 and max 1"
# Max absolute scalar
Same as mi

# Robust...?
preserves whether values are pos or neg

# Normalizer

#look_into
Sometimes you can scale the entire sample by the norm IF the sample has all numerical values. Each value gets divided by the norm of the vector