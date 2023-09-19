# This is a demo for how the co-occurrence and exclusion time scale are obtained for the study. 


![Fig3_v5](https://github.com/Debbcwing/SbNPZD_Exclusion/assets/51200142/19a6ca40-f9f9-494f-8550-4b94c9dd81ce)



For example, 'Pbio' is an array of phytoplankton biomass under a certain scenario (e.g. oligotrophic, eutrophic, or hypertrophic condition) for 365 days. 

### Phytoplankton size classes - 365 days ###
This shows the temporal changes of phytoplankton size classes with biomass concentration above 0.01 µmol N L-1

````
for d in range(365):
  numSC = sum(Pbio[d] >= 1e-2)
````
'numSC' is the output array (in this case, a one-dimension array) with a length of 365 containing the number of size classes for each day.


### Phytoplankton co-occurrence ###
This index measures the average number of phytoplankton size class over a certain period (e.g. 30 days, 60 days etc.)

````
Cooccurr = np.mean(numSC[0:30])
````
'Cooccurr' is the output (in this case, only one number) containing the co-occurrence.


### Phytoplankton exclusion time scale ###
Here we want to calculate the time (days) it takes to exclude (temporarily) a certain fraction (e.g. 80%) of the size classes appeared at day 0. 

````
excluTS = sum(numSC[:] >= (150 * 0.8))
````
'excluTS' is the output (in this case, only one number) containing the exclusion time scale.
